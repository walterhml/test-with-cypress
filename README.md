# Documentação Técnica - Teste Cypress

## Visão Geral
Este documento descreve um teste automatizado utilizando Cypress, uma ferramenta de teste end-to-end para aplicações web. O teste em questão tem como objetivo verificar a funcionalidade de preenchimento de um campo de e-mail em uma página web.

## Teste
O teste em questão está encapsulado em uma suíte de testes chamada "My First Test". Ele realiza as seguintes etapas:

1. **Visita à Página Web**: O teste começa visitando a página web `https://example.cypress.io`.
2. **Clique no Elemento 'type'**: O teste localiza e clica no elemento que contém o texto 'type'.
3. **Verificação da URL**: Após o clique, o teste verifica se a URL atual contém '/commands/actions', garantindo que a navegação foi realizada com sucesso para a seção correta da página.
4. **Preenchimento do Campo de E-mail**: O teste localiza um campo de entrada de texto com a classe `.action-email` e insere o texto 'fake@email.com'.
5. **Verificação do Valor do Campo de E-mail**: Por fim, o teste verifica se o valor inserido no campo de e-mail é de fato 'fake@email.com'.

## Estrutura do Teste
O teste está estruturado utilizando o padrão BDD (Behavior Driven Development), com a função `describe` para agrupar os testes e a função `it` para descrever cada caso de teste individualmente. Abaixo está a estrutura do teste:

```javascript
describe('My First Test', () => {
  it('Gets, types and asserts', () => {
    // Passo 1: Visita à Página Web
    cy.visit('https://example.cypress.io')

    // Passo 2: Clique no Elemento 'type'
    cy.contains('type').click()

    // Passo 3: Verificação da URL
    cy.url().should('include', '/commands/actions')

    // Passo 4: Preenchimento do Campo de E-mail
    cy.get('.action-email').type('fake@email.com')

    // Passo 5: Verificação do Valor do Campo de E-mail
    cy.get('.action-email').should('have.value', 'fake@email.com')
  })
})
