# 🎨 Mini Tutorial – Sass do Básico ao Essencial

## 🔹 1. O que é Sass?
Sass significa **Syntactically Awesome Stylesheets**.  
É um **pré-processador de CSS**, ou seja, uma camada extra que adiciona novas funcionalidades ao CSS (como variáveis, aninhamento, mixins e importações). No final, ele **sempre gera um CSS comum**, que o navegador entende.  

### 📌 Por que o Sass surgiu?
O CSS tradicional, por volta de **2006–2007**, tinha muitas limitações:  
- Não existiam **variáveis** (era preciso repetir cores e tamanhos em vários lugares).  
- O código CSS ficava **grande e difícil de manter** em projetos grandes.  
- Não havia recursos para **organização e reutilização de código**.  

O Sass foi criado em **2006 por Hampton Catlin** e rapidamente adotado por desenvolvedores porque trouxe **organização, reaproveitamento e produtividade** ao CSS.  

### 🔗 Saiba mais
👉 Documentação oficial: [https://sass-lang.com](https://sass-lang.com)  

 

---

## 🔹 2. Instalação e uso

**Instalar (uma vez só):**
```

npm install -g sass

```
### Compilar manualmente:
```

sass assets/scss/style.scss assets/css/style.css

```
Pega o `style.scss` e gera o `style.css`.

### Modo automático (observação):
```

sass --watch assets/scss:assets/css

```
O Sass recompila sozinho toda vez que você salvar.

## 🔹 3. Variáveis

**O que são:**
São “apelidos” para guardar valores (cor, fonte, tamanho).

Exemplo:
```sass
$primary-color: #3498db;
$font-stack: 'Arial', sans-serif;

body {
  background: $primary-color;
  font-family: $font-stack;
}

```
> resultado da saída CSS
```css
body {
  background: #3498db;
  font-family: "Arial", sans-serif;
}
```
**Vantagens:**
- Consistência visual (mesmas cores/fontes em todo site).
- Alterações rápidas (muda só na variável e vale para tudo).

## 🔹 4. Alinhamento
**O que é:**
Permite escrever seletores dentro de outros, representando a hierarquia do HTML.

**Exemplo:**
```sass
nav {
  background: #eee;

  ul {
    list-style: none;
  }

  a {
    color: blue;
    text-decoration: none;
  }
}
```
> resultada de saída CSS
```css
nav {
  background: #eee;
}
nav ul {
  list-style: none;
}
nav a {
  color: blue;
  text-decoration: none;
}
```

**Vantagens:**

- Código mais organizado e limpo.
- Facilita visualizar a relação entre elementos.
- Evita repetição de seletores longos.

## 🔹 5. Importação de arquivos

**O que é:**
Você pode dividir seu CSS em arquivos menores e depois juntar tudo em um só para compilar.

**Exemplo** (`style.scss`):
```sass
@use 'layout';
@use 'design';
```
### Estrutura de pastas:
```
scss/
  ├── layout.scss
  ├── design.scss
  └── style.scss  // importa os outros
css/
  └── style.css   // gerado automaticamente
```
**Vantagens:**

- Melhor organização (cada arquivo com sua função).
- Facilita manutenção e entendimento do projeto.

## 🔹 6. Mixins
**O que são:**
São blocos de código reutilizáveis que você cria uma vez e aplica em vários lugares.

**Exemplo:**
```sass
@mixin centralizar {
  display: flex;
  justify-content: center;
  align-items: center;
}

header {
  @include centralizar;
}
```
> saída CSS
```css
header {
  display: flex;
  justify-content: center;
  align-items: center;
}
```

**Vantagens:**
Reutiliza código sem copiar e colar. Ideal para estilos repetitivos (centralização, botões, sombras).

## 7. Extends

**O que é:**
Permite **herdar estilos de outra classe.**

**Exemplo:**
```sass
.botao {
  padding: 10px;
  border-radius: 5px;
}

.botao-primario {
  @extend .botao;
  background: blue;
  color: white;
}
```
> saída CSS
```css
.botao, .botao-primario {
  padding: 10px;
  border-radius: 5px;
}

.botao-primario {
  background: blue;
  color: white;
}
```

**Vantagens:**

- Economiza código repetido.
- Cria famílias de estilos baseados em uma classe principal.

## 🔹 8. Estrutura recomendada

**Estrutura de projeto sugerida:**
```
projeto/
├── index.html
├── assets/
│   ├── css/
│   │   └── style.css     (gerado)
│   ├── scss/
│   │   ├── layout.scss
│   │   ├── design.scss
│   │   └── style.scss    (importa os outros)
│   └── img/
```
