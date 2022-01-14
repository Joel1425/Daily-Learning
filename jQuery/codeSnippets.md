##### Serialize all form data to JSON
```html
// html
<form id='form-submit'>
  ...
</form>
```
```javascript
// jQuery
$.fn.serializeFormJSON = function () {
    var o = {};
    var a = this.serializeArray();
    $.each(a, function () {
        if (o[this.name]) {
            if (!o[this.name].push) {
                o[this.name] = [o[this.name]];
            }
            o[this.name].push(this.value || '');
        } else {
            o[this.name] = this.value || '';
        }
    });
    return o;
};

  const dataJson = $('#form-submit').serializeFormJSON();         // serialize all data to JSON
  console.log('dataJson: ', dataJson);                            // output
```
##### Use multiple events listener
```javascript
$('.cpu-val').on('keypress keyup', function () {
           // Code here
});
```

#### Remove/hide page fade-in due to modal call
`<div class="modal-backdrop fade in" style="display: none;"></div>` is responsible for page fade in. Sometimes modal window gone but
page fade-in remains.
```js
$('.modal-backdrop').hide();
```

#### Miscellaneous
```
// jQuery's data() does not update the attributes, it sets an internal data object, but uses the data attribute as the default value only.
// use .attr()
.attr('data-name')        

// Manually trigger an element
$('.class-name').on('click', function() {
    $('.class-name').trigger('triggerWord');          // now backbone grab the event listener, backbone  
} 

// Get the `type` of an `input field` by searching `name` attribute
$("input[name='field-name']").attr('type'); 

// Get the value of checkbox
const check = $('#id').prop('checked');
```