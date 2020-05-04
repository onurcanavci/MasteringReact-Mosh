#Components
---
## Rendering Classes Dynamically (Video 7)

```javascript
class Counter extends Component {
  state = {
    count: 0
   };
   
   render() {
    return(
      <div>
        // if count equals to zero, className equals to "badge m-2 badge-warning"
        // otherwise "badge m-2 badge-primary"
        <span> className={this.getBadgeClasses()}>{this.formatCount()}</span>
        <button className="btn btn-secondary btn-sm">Increment</button>
      </div>
    );
}

getBadgeClasses() {
  let classes = "badge m-2 badge-";
  classes += this.state.count === 0 ? "warning" : "primary";
  return classes;
}

formatCount() {
  const { count } = this.state;
  return count === 0 ? <h1>Zero</h1> : count;
}


```
 
