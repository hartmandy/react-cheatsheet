#React cheat sheet

componentDidMount()
componentDidUpdate()
componentWillUnmount()

useState - when data changes, rerender UI
const [count, setCount] = useState(initial state)

useEffect - runs when mounted or when state changes, takes function as argument and looks for dependencies to see state changes; running side effects on functional component
useEffect(() => {
alert(‘hello side effect’)
}, [array of dependencies])

useContext - share data without passing props, consumes value from nearest parent provider
const mood = useContext(MoodContext) <Provider or Consumer/>

useRef = keeps reference on object between renders; mutable value does not trigger rerender of UI
OR to grab native HTML elements from JSX/ DOM
const myButton = useRef(null)

useReducer - Redux, a different way to manage state; dispatch actions (type, payload) to reducer function, reducer function looks to store to see how to compute next state; switch statement with cases
const [state, dispatch] = useReducer(reducer, initial state)

useMemo - memoization, cache result of function call to deal with expensive computations
const expensiveCount = useMemo(() => {
return count \*\* 2;
}, [count])

useCallback - memoize functions but preventing unnecessary rerenders; optimize performance
const memoizeFunction = useCallback(()=>{
//function logic
}, [dependency1, dependency 2])

useImperativeHandle - forward reference to element, modify exposed ref
