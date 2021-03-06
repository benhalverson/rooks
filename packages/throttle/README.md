# @rooks/use-throttle

### Throttle custom hook for React

### Installation

```
npm install --save @rooks/use-throttle
```

### Importing the hook

```javascript
import useThrottle from "@rooks/use-throttle"
```

### Usage

```jss
function ThrottleDemo() {
  const [number, setNumber] = useState(0);
  const addNumber = () => setNumber(number + 1);
  const [addNumberThrottled, isReady] = useThrottle(addNumber, 1000);
  // isReady is a boolean that tells you whether calling addNumberThrottled at that point
  // will fire or not.
  // Once the timeout of 1000ms finishes, isReady will become true to indicate that the next time 
  // addNumberThrottled is called it will run right away.
  return (
    <>
      <h1>Number: {number}</h1>
      <p>Click really fast.</p>
      <button onClick={addNumber}>Add number</button>
      <button onClick={addNumberThrottled}>Add number throttled</button>
    </>
  );
}
```


### Arguments

| Argument            | Type     | Description                         | Default value |
| ------------------- | -------- | ----------------------------------- | ------------- |
| callback (required) | function | Function that needs to be throttle  | undefined     |
| timeout (optional)  | number   | Time to throttle the callback in ms | 300           |

