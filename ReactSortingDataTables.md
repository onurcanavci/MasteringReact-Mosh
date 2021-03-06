#Sorting
---
## Sorting DataTables using React and JSON (https://www.youtube.com/watch?v=akxsFgM7DPA)

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
 ## Rendering Lists (Video 8)
```javascript
class Counter extends Component {
  state = {
    count: 0,
    tags: ["tag1", "tag2", "tag3"]
   };
   
   render() {
    return(
      <div>
        <span> className={this.getBadgeClasses()}>{this.formatCount()}</span>
        <button className="btn btn-secondary btn-sm">Increment</button>
        <ul>{this.state.tags.map(tag => <li key={tag}>{tag}</li>)}</ul>
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

  ## Conditional Rendering (Video 9)
```javascript
class Counter extends Component {
  state = {
    count: 0,
    tags: ["tag1", "tag2", "tag3"]
   };
   
   renderTags() {
     if(this.state.tags.length === 0) return <p> There are no tags!</p>
    
     return <ul>{this.state.tags.map(tag => <li key={tag}>{tag}</li>)}</ul>;
   }
   render() {
    return(
      <div>
        {this.state.tags.length === 0 && "Please create a new tag!"}
        {this.renderTags()}
      </div>
    );
}

```

