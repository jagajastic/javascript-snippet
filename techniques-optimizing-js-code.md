# Find the full explanation from [JS Techniques](https://www.codesmith.io/blog/top-10-techniques-for-javascript-performance-optimization#dom)

### DOM Manipulations

<code>
  const fragment = document.createDocumentFragment();
  for(let i = 0; i < 100; i++){
    const newItem = document.createElement("div");
    newItem.textContent = `Item ${i + 1}`;
    fragment.appendChild(newItem);
  }

  document.getElementById('container').appendChild(fragment);
  
</code>

### Use efficient looping patterns
always use for loop for iteration.

<code>
  const arr = [1,2,3,4,5,6];
  for(let i = 0; i < arr.length; i++){
      console.log(arr[i]);         
     // exist when needed                
    if(arr[I] % 2 === 0) return;                 
  }
</code>

### Optimize object and array access
// inefficient example 
for(let i=0; i < items.length; i++){
  console.log(items[i])
}

// efficient example 
const len = items.length;
for(le i =0; i < len; i++){
  const item = items[i]
  console.log(item.name)
}

<b>Accessing value from array</b>
<code>
  let users = [
      {id: 1, name: "John", age: 32 },
      {id: 1, name: "Doe", age: 23 },
      {id: 1, name: "James", age: 20 },
      {id: 1, name: "Mary", age: 31 },
  
  ]

  <b>Iteration example</b>
  let foundUser = null;
  for(let i=0; i<users.length; i++){
    if(users[i].id === 2) {
      foundUser = users[i];
      break;
    }
  }

  <b>declarative using objects</b>
  let newUsers = {
      1:{id: 1, name: "John", age: 32 },
      2:{id: 2, name: "Doe", age: 23 },
      3:{id: 3, name: "James", age: 20 },
      4:{id: 4, name: "Mary", age: 31 },
  
  }
  let foundUser = newUsers[2]
</code>




