```
//= require JODY/base
//= require ./jody_notificator_init
```

jody_notificator_init.js.coffee

```coffee
@JodyNotificator.clean = ->
  Notifications.clean()

@JodyNotificator.error = (error) ->
  Notifications.show_error(error)

@JodyNotificator.errors = (errors) ->
  Notifications.show_errors(errors)

@JodyNotificator.flashs = (flashs) ->
  Notifications.show_flash(flashs)

@JodyNotificator.flash = (method, _msg) ->
  flashs = {}
  flashs[ method ] = _msg
  Notifications.show_flash(flashs)
```

```
doc = $ document

doc.on 'ajax:success', '#form', (xhr, data, status) ->
  JODY.processor(data)
```

```
json.set! :keep_alerts, true

json.set! :flash, {
  notice: "Публикация назначена в раздел"
}
```

```
json.set! :keep_alerts, true

json.set! :flash, {
  warning: "При загрузке возникли ошибки"
}

json.errors @attached_image.errors
```


```ruby
json.set! :html_content, {
  set_html: {
    "#some_block" => "Hello World!",
  },
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
