# Lista 1

## Lista 1 - Evolução Responsiva do Portfólio (Sass + GitHub + Vercel + Figma)

DESCRIÇÃO

Time de front, vamos tirar o site do modo “desktop-only” e alinhar com o design de Figma. A missão é implementar a versão responsiva do portfólio, aderente aos tokens e componentes definidos no Figma. Sem “achismos”: seguir especificações do Figma. Tolerância de desvio visual: ±4px. Se algo não estiver claro no Figma, priorize consistência com os padrões já definidos nos frames.

Objetivo de negócio: entregar UX consistente em mobile e desktop, com acessibilidade AA, performance saudável e pipeline de deploy automático.


O QUE DEVE SER FEITO:

1. Novo arquivo Sass: assets/scss/responsive.scss
Importar em style.scss (ponto de entrada).
2. Breakpoint único base: 668px
Use media queries concentradas em responsive.scss.
3. Menu responsivo:
Até 667px: menu colapsado (hambúrguer), navegação por teclado funcional, foco visível.
≥ 668px: menu horizontal conforme Figma.
4. Layout responsivo conforme Figma:
Reorganizar grids/containers/cards nos estados <668px e ≥668px seguindo espaçamentos, colunas e tipografia indicados no Figma.
Sem valores “mágicos”: reutilize tokens/variáveis já existentes.

Estrutura de como ficará:

assets/scss/
|-- style.scss
|-- design.scss
|-- layout.scss
|-- responsive.scss

Exemplo mínimo (não é guia e nem receita, apenas dica):

/* responsive.scss */
@media (min-width: 668px) {
  .navbar { /* desktop/tablet */ }
  .navbar__toggle { display: none; }
  .grid { /* colunas/gutters conforme Figma */ }
}

@media (max-width: 667.98px) {
  .navbar { /* mobile */ }
  .navbar__menu { /* offcanvas/overlay, focável, escapável com Esc */ }
  .card-list { /* 1 col */ }
}

ENTREGA:
Link do commit da tarefa no repositório no GitHub (no fork e branch do aluno);
Link do site publicado no Vercel.