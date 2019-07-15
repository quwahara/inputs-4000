# Inputs 4000

## Abstract

Software keyboard show-up delays on iOS Safari in specific case.
This is the proof codes for it.

## Reproduce

There is a `<div>` that has `style="display: none;"`.
It calls none-div.
Put 4,000 of `<div>` under none-div that has `<input type="checkbox">` and `<input type="text">`.
Put `<input type="text" name="input1">` over none-div.
Touch `<input type="text" name="input1">`.
It takes around 15sec to show up software keyboard.

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

* If `<div>` has `style="display: block;"`.
* If the 4,000 of `<div>` has only `<input type="checkbox">`.
* If the 4,000 of `<div>` has only `<input type="text">`.

I hope to fix this, thanks.

## License

This software is released under the MIT License, see LICENSE.
