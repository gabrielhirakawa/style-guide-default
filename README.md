# Style Guide - VSCODE :boom:
Configuração default de style guide.

### 1 - Gerar .editorconfig
Clicar com botão direito no diretório raíz do VSCODE e ***Generate .editorconfig*** (Necessário ter extensão do EditorConfig instalada).
Dentro do arquivo copiar o código:
```
root = true

[*]
end_of_line = lf
indent_style = space
indent_size = 2
charset = utf-8
trim_trailing_whitespace = true
insert_final_newline = true
```

### 2 - Delete eslint
Apagar arquivo do eslint se houver e instalar o eslint como depedência de desenvolvimento:
```
yarn add eslint -D
yarn eslint --init
```

### 3 - Delete package-lock
Apagar aquivo ***package-lock.json*** para associar as dependências ao arquivo ***yarn.lock*** e reinstalar utilizando o comando abaixo:
```
yarn 
```

### 4 - Install Prettier
Instalar dependências do prettier e babel-eslint conforme abaixo:
```
yarn add prettier eslint-config-prettier eslint-plugin-prettier babel-eslint -D 
```

### 5 - Add to eslintrc
No arquivo ***.eslintrc.js*** copiar as configurações:
```
module.exports = {
  env: {
    es6: true,
  },
  extends: ['plugin:react/recommended', 'airbnb', 'prettier/react'],
  globals: {
    Atomics: 'readonly',
    SharedArrayBuffer: 'readonly',
  },
  parser: 'babel-eslint',
  parserOptions: {
    ecmaFeatures: {
      jsx: true,
    },
    ecmaVersion: 2018,
    sourceType: 'module',
  },
  plugins: ['react', 'prettier'],
  rules: {
    'linebreak-style': 0,
    'prettier/prettier': 'error',
    'react/jsx-filename-extension': [
      'warn',
      {
        extensions: ['.jsx', '.js'],
      },
    ],
    'import/prefer-default-export': 'off',
  },
};
```

### 6 - Add to prettierrc
Criar arquivo ***.prettierrc*** com configurações de single quote:
```
{
'singleQuote': true,
'trailingComma': "es5"
}
```

### 7 - Add to settings
Para que as configurações sejam aplicadas ao salvar o arquivo, no arquivo principal de configurações do VSCODE ***settings.json*** (ctrl + shift + P) adicione a seguinte linha:
```
'eslint.autoFixOnSave': true
``` 


Ambiente configurado! Só começar a codar. :coffee: :raised_hands: 
