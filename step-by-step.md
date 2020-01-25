- gerar o editor config
  -- end_of_line = lf
- yarn add eslint -D
- yarn eslint --init

```javascript
{
  extends:[
    'airbnb',
    'prettier',
    'prettier/react'
  ],
  parser: 'babel-eslint',
  plugin: [
    'react',
    'prettier'
  ],
  rules:[
    'prettier/prettier': 'error',
    'react/jsx-filename-extension': [
      'warn',
      { extensions: ['.jsx','js']}
    ],
    'import/prefer-default-export': 'off'
  ]
}
```

- yarn add prettier eslint-config-prettier eslint-plugin-prettier babel-eslint -D

```javascript
.prettierrc
  {
    'singleQuote': true,
    'traillingComma': 'es5'
  }
```

- yarn add react-router-dom
  -- rotas
