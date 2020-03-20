# ![Laravel Nova Html Field](https://github.com/joshmoreno/nova-html-field/raw/master/example.png)

A nova field for rendering html on all resource pages: index, detail, and forms. This is hopefully a temporary solution until nova supports computed fields on forms.

## Install
```
composer require joshmoreno/nova-html-field
```

## Usage
### Inline string
```php
\JoshMoreno\Html\Html::make('Some Title')
    ->view('<h1>Example</h1>'),
```

### Closure
```php
\JoshMoreno\Html\Html::make('Some Title')
    ->html(function() {
        return "<h1>$this->name</h1>";
    }),
```

### View
```php
\JoshMoreno\Html\Html::make('Some Title')
    ->view('fields.example'),
```

### View with access to model attributes
```php
\JoshMoreno\Html\Html::make('Some Title')
    ->html(function() {
        return view('fields.example')
                 ->with('name', $this->name)
                 ->render();
    }),
```