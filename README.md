
# useDebounce (A ReactJS Hook)

## This is a react-JS hook.

 It is basically useful to add **debounce/delay** until some task is happening, once the task will be done then provided **callback** will be executed.

### Debounced provided callback function for particular interval

```mermaid
import { useDebounce } from "use-debounce-rv/dist";

const { Debounce } = useDebounce();

Debounce(() => {}, 1000);
```


# Installation

```mermaid
npm i use-debounce-rv
```
or

```mermaid
npm i --legacy-peer-deps use-debounce-rv
```

##  Usage example

### Import Hook

    import { useDebounce } from  'use-debounce-rv/dist';
### Define Hook

    const { Debounce } = useDebounce();
    
### Usage

   >Debounce(callback, interval)
   >> **callback**: *A function to execute after particular interval.*
   >> **interval**: *Time in milli seconds.*

    Debounce(() => {}, 1000);

## Example -01 (Execute a callback after typing finished)

```mermaid
import { useDebounce } from "use-debounce-rv/dist";

export const SamplePage = () => {
	const [data, setData] = useState();
	const { Debounce } = useDebounce();

	const handleChange = (e) => {
		setData(e.target.value);
		//Debounce(callback, interval)
		//Debounce(() => {}, 1000);
		Debounce(() => {
			console.log("side effect after typing finshed");
		}, 1500);
	};
	return (
		<div>
			<label>Search Data</label>
			<input type="text" value={data} onChange={handleChange} />
		</div>
	);
};
```

> In above example Debounce will execute the console.log once user ends typing.

## Example - 02 (Add delay in function execution)

```mermaid
import { useDebounce } from "use-debounce-rv/dist";

export const SamplePage = () => {
	const { Debounce } = useDebounce();

	const handleClick = (e) => {
		//Debounce(callback, interval)
		//Debounce(() => {}, 1000);
		Debounce(() => {
			console.log("I am executed after 2 second");
		}, 2000);
	};
	return (
		<div>
			<label>Click The Button </label>
			<button onChange={handleClick}>Hey! Click Me</button>
		</div>
	);
};
```

> In above example Debounce will execute the console.log after 2 second.

