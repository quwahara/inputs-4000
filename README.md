# Inputs 4000

## Abstract

Software keyboard show-up delays on iOS Safari in a specific case.
This is the proof codes for it.

## Reproduce

There is a `<div>` that has `style="display: none;"`.  
It calls 'none-div' in later.  
Put 4,000 of `<div>` under none-div that has `<input type="checkbox">` and `<input type="text">`.  
Put `<input type="text" name="input1">` over none-div.  
Touch `<input type="text" name="input1">`.  
It takes around 15sec to show up software keyboard.  

The example page: [https://quwahara.github.io/inputs-4000/cb-txt-4000-none.html](https://quwahara.github.io/inputs-4000/cb-txt-4000-none.html)

## Example

```html
<!DOCTYPE html>
<html>

<head>
  <meta charset="UTF-8">
  <link rel="icon" href="data:,">
  <title>CB TXT 4000 None</title>
</head>

<body>
  <div>
    <h1>CB TXT 4000 None</h1>
    <div>
      <label for="input1">input1</label>
      <input type="text" name="input1">
    </div>
    <div>
      <label for="input2">input2</label>
      <input type="text" name="input2">
    </div>
  </div>
  <div style="display: none;">
    <!-- Repeats below line 4,000 times -->
    <div><input type="checkbox"><input type="text"></div>
  </div>
</body>

</html>
```

## Environments

iPad mini (5th generation)
iOS 12.3.1

## Supplements

It doesn't happen:

* If `<div>` has `style="display: block;"`.  The page is: [https://quwahara.github.io/inputs-4000/cb-txt-4000-block.html](https://quwahara.github.io/inputs-4000/cb-txt-4000-block.html)
* If the 4,000 of `<div>` has only `<input type="checkbox">`.  The page is: [https://quwahara.github.io/inputs-4000/cb-4000-none.html](https://quwahara.github.io/inputs-4000/cb-4000-none.html)
* If the 4,000 of `<div>` has only `<input type="text">`.  The page is: [https://quwahara.github.io/inputs-4000/txt-4000-none.html](https://quwahara.github.io/inputs-4000/txt-4000-none.html)

I hope to fix this, thanks.

## License

This software is released under the MIT License, see LICENSE.
