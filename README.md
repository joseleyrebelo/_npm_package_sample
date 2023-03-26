# Todo - Improvements

- Introduce `validateStrategy` to `<Form>` as `<Form options={{validateStrategy}}>`
  - or potentially as `<Form validateStrategy={"iteratedOn" | "withContent"}>`
  - Strategy `iteratedOn` allows the validation run (display error/success) for every action after the first one
  - Strategy `withContent` allows the validation run (display error/success) for every action after the first one
  - Strategy `iteratedOn+withContent` (both mentioned before)
    - Will be/require third factor `onSubmit` - only show error after submit
    - Asks for `onFocusOutPostSubmit`

# Todo - tests

- Without a formContext

# Bugs

- useState seems to be running before React component,
  - could have to do with importing Form
- ```
  // Submit.tsx
  useEffect(() => {
    if (formContext) {
      setHasDefaultStyle(formContext.config().defaultStyle);
    }
  }, [formContext]);
  ```
  adding formContext to the useEffect watch creates infinite loop
  likewise in Input.tsx
