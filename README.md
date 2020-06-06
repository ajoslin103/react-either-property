### purpose

This utility was created to help verify my React component props in the situations where either one or the other of two props are expected (or required.)

## installation

`npm install react-either-property`

### example

In this contrived example we can use 1-2 of 4 params 

We require either a Northerly or Southerly amount, and would use either of an Easterly or Westerly amount if available

```
import { EitherOptional, EitherRequired } from 'react-either-property';

function ComponentSeven({ north, south, east, west }) {
  [component code here]
}

ComponentSeven.propTypes = {
  east: PropTypes.number,
  west: PropTypes.number,
  north: PropTypes.number,
  south: PropTypes.number,
  ignored: EitherOptional('north', 'south'),
  undefined: EitherRequired('north', 'south'),
};
```

This code uses the React Props' systems custom validators -- Note: the supplied props names are ignored, the behavior when those names match actual passed props is knknown and undefined

## testing

you can call the internal test() function which will console it's results
