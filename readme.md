# Fox Template Engine Manual

## Install
1. Open your project in terminal
2. activate virtual env
3. Input 'pip install foxTemplateEngine'

## How to use?
```python
from foxTemplateEngine.template_engine import FoxEngine # transform() is a func for render your template to vanilla HTML

obj = FoxEngine('path', {}) # 'path' - path to template, {} - context
obj.getRenderedTemplateAsText() # getting a rendered template
obj.writeToFile('new_path') # saving to file by path: new_path
```

## Example
### Before (project/test.fox)
```html
/body
 % repeat 4 %
 /h1
  {{ context['var'] }}
   START LOOP
   % repeat 2 %
   LOOOOOOOP
   % end %
   END LOOP
 ./h1
 % end %
./body
```
### Start this code
```python
from foxTemplateEngine.template_engine import transform

obj = FoxEngine('test.fox', {
    'var': 'Hello, World!'
})
obj.getRenderedTemplateAsText()
obj.writeToFile('test.html')

"""
function getRenderedTemplateAsText() is called first and only then writeToFile()
"""
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