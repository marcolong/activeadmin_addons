# Select2

## Search

To enable select2 search functionality you need to do the following:

```ruby
  f.input :category_id, as: :search_select, url: admin_categories_path,
          fields: [:name, :description], display_name: 'name', minimum_input_length: 2,
          allow_clear: true, placeholder: 'Insert an element...'
```

<img src="./images/select2-search-select.gif" />

### Options

* `category_id`: Notice we're using the relation field name, not the realtion itself, so you can't use `f.input :category`.
* `url`: This is the URL where to get the results. This URL expects an activeadmin collection Url (like the index action) or anything that uses [ransack](https://github.com/activerecord-hackery/ransack) search gem.
* `fields`: an array of field names where to search for matches in the related model (`Category` in this example). If we give many fields, they will be searched with an OR condition.
* `display_name`: **(optional)** You can pass an optional `display_name` to set the field to show results on the select. This will be the field read from the object on loading the form and also when reading data from the ajax response(on the JSON). It **defaults to**: `name`
* `minimum_input_length`: **(optional)** Minimum number of characters required to initiate the
  search. It **defaults to**: `1`
* `class`: **(optional)** You can pass extra classes for your field.
* `allow_clear`: **(optional)** You can remove an already chose element.
* `placeholder`: **(optional)** You can pass a placeholder.
