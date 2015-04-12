```ruby
json.set! :html_content, {
  append: {
    "@test_append_1" => "Test append/1",
    "@test_append_2" => "Test append/2",
    "@test_append_3" => "Test append/3"
  },
  replace: {
    "@test_replace_1" => "Text for replace/1",
    "@test_replace_2" => "Text for replace/2",
    "@test_replace_3" => "Text for replace/3"
  },
  destroy: [ "@test_destroy_1", "@test_destroy_2", "@test_destroy_3" ],

  attrs: {
    append: {
      '@test_attrs' => { 'data-title' => "Hello world!", alt: "New Picture", title: "New Picture" }
    },
    replace: {
      '@test_attrs' => { src: "https://avatars0.githubusercontent.com/u/496713" }
    },
    destroy: {
      '@test_attrs' => [ :title, :alt ]
    }
  }
}

json.set! :js_exec, [
  { "console.log" => "hello world!" },
  { "console.log" => { test: 1, test_2: 2 } }
]

json.page_reload  true
json.redirect_to  '/path'
json.replace_with '/path'
```
