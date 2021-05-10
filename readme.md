# Fox Template Engine Manual

## Install
1. Open your project in terminal
2. activate virtual env
3. Input 'pip install foxTemplateEngine'

## How to use?
```python
from foxTemplateEngine.template_engine import transform # transform() is a func for render your template to vanilla HTML

transform('test', {}) # test - path to your file, {} - context
```

## Example
### Before (project/test)
```html
body
 % repeat 4 %
 h1
  {{ context['var'] }}
   START LOOP
   % repeat 2 %
   LOOOOOOOP
   % end %
   END LOOP
 .h1
 % end %
.body
```
### Start this code
```python
from foxTemplateEngine.template_engine import transform

transform('test', {
  'var': 'Hello, World!',
})
```
### After (project/test.html)
```html
<body>
 <h1>
  Hello, World!
   START LOOP
   LOOOOOOOP
   LOOOOOOOP
   END LOOP
 </h1>
 <h1>
  Hello, World!
   START LOOP
   LOOOOOOOP
   LOOOOOOOP
   END LOOP
 </h1>
 <h1>
  Hello, World!
   START LOOP
   LOOOOOOOP
   LOOOOOOOP
   END LOOP
 </h1>
 <h1>
  Hello, World!
   START LOOP
   LOOOOOOOP
   LOOOOOOOP
   END LOOP
 </h1>
</body>
```

## See tests for a better understanding of how the package works!