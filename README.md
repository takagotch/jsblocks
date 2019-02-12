### jsblocks
---
https://github.com/astoilkov/jsblocks

```
<input data-query="val(newTodo)">

<input data-query="val(fisrname)">
<input data-query="val(lastName)">
{{firstName}} {{lastName}}

{{title}}

<span data-query="visible(editing)" class="value-holder">
{{name}}
</span>
<span data-query="visible(editing)" class="value-holder">
  <input data-query="val(name)">
</span>
<span class="button-holder">
  <span data-query="click(toggleEdit)">
    {{editing() ? 'Update' : 'Edit'}}
  </span>
  <span data-query="click(remove)" class="btn-delete">Delete</span>
</span>

```

```js
this.newTodo = blocks.observable();

blocks([1, 2, 3]).map(/* code */)
  .filter()
  .each()();

blocks.query({
  firstname: blocks.observable('John'),
  lastName: blocks.obserable('Doe')
});

var App = blocks.Application();

var product = App.Model({
  name: App.Property(),
  
  editing: blocks.obserable(false),
  
  toggleEit: function () {
    this.editing(!this.editing());
  },
  
  remove: function () {
    this.destroy(true);
  }
});

var Products = App.Collection(Product);

App.View('Products', {
  newProduct: Product(),
  
  products: Products([{ name: 'HTML' }, { name: 'CSS' }, { name: 'JavaScript' }]),
  
  keydown: function (e) {
    if (e.which == 13) {
      this.products.add(this.newProduct);
      this.newProduct.reset();
    }
  }
});
```

```css
#products > input {
  font-size: 16px;
  padding: 12px 16p;
  width: 326px;
  background: #ddf4e8;
  border: 1px solid #54b07e;
}
.result-wrap {
  margin-top: 10px;
  border: 1px solid #dcdcdc;
  background: #fbfbfb;
  width: 360px;
}
.result-wrap .buttons-holder {
  display: table-cell;
}
.button-holder > span {
  cursor: pointer;
  margin-left: 10px;
  color: #2d8dc4;
}
.button-holder .btn-delete {
  color: #e65f5f;
}
.result-wrap .value-holder {
  display: table-cell;
  border-right: 1px solid #dcdcdc;
  width: 220px;
  padding: 10px;
}
```

