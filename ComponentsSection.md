#Components
---
## Rendering Classes Dynamically (Video 7)

Table Component
```javascript
import React from 'react';

export default function CoinTable(props) {
  return(
    <table>
      <thead>
        <th>#</th>
        <th>Name</th>
        <th>Symbol</th>
        <th>
          <button
            onClick={()=> props.sortBy('price_usd')}
          >
            Price
          </button>
        </th>
      </thead>
      <tbody>
        {
          props.data.map(row=> (
            <tr>
              <td>{row.rank}</td>
              <td>{row.name}</td>
              <td>{row.symbol}</td>
              <td>{row.price_usd}</td>
            </tr>
          ))
        }
      </tbody>
    </table>
  )
}
```

App containers

```javascript
import React from 'react';
import CoinTable from './components/coin-table';

import data from './data/coins.json';

class App extends React.Component {
  constructor(props){
    super(props)
    this.state = {
      data: data,
      direction: {
        price_usd: 'asc',
      }
    }
    this.sortBy = this.sortBy.bind(this);
  }
  
  sortBy(key){
    this.setState({
      data: data.sort((a,b)=>(
        this.state.direction[key] ==='asc'
          ? parseFloat(a[key]) - parseFloat(b[key])
          : parseFloat(b[key]) - parseFloat(a[key])
      )),
      direction: {
        [key]: this.state.direction[key] === 'asc'
          ? 'desc'
          : 'asc'
      }
    })
  }
  
  render() {
    return(
      <div
        className="page-container"
      >
        <CoinTable 
          data={this.state.data}
          sortBy={this.sortBy}
        />
      </div>
    )
  }
  
}

export default App;


```



