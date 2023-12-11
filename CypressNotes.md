Cypress Notes
---

Cypress is the E2E testing suite I use for the frontend of DivaScore. These are my notes on such things.

## Set up a command for login
- In commands use `cy.request` to do the logic you're doing on your FE

```
Cypress.Commands.add('login', () => {
  cy.request({
    method: 'POST',
    url: cy.env('url'),
    body:
    ... etc


  })
  .then((resp) => {
    window.localStorage.setItem('jwt', resp.body.user.token)
  })
})