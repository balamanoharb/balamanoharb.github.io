https://www.youtube.com/watch?v=dpw9EHDh2bM

- Reusing Logic -> higher order components -> changes the tree structure and harder to debug -> Wrapper Hell
- Giant components
- Confusing classes for both humans and machine

https://legacy.reactjs.org/blog/2016/07/13/mixins-considered-harmful.html


- hooks should be at the top of function
- it shouldn't be under any condition as it depends on the order of hooks.

how to use state
useContext. how to use context (eg: Theme, Locale)
useEffect. how to make side effects (componentDidMount, componentDidUpdate, componentWillUnmount) -> runs after initial render and after every render