# USP - ITC - Decidibilidade

> Catálogo de problemas decidíveis e indecidíveis para a matéria Introdução à Teoria da Computação

## Problemas decidíveis

<table>
  <thead>
    <tr>
      <th>Problema</th>
      <th>Linguagem</th>
      <th>Máquina de Turing</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Aceitação de uma cadeia por um AFD</td>
      <td>$A_{AFD} = \{ (B,w) | B$ é um $AFD$ que aceita a cadeia $w \}$</td>
      <td>$M_{A_{AFD}} =$ "Sobre a entrada $(B,w)$, onde $B$ é um $AFD$ e $w$ é uma cadeia:
        <ol>
          <li>Simule $B$ sobre a cadeia $w$</li>
          <li>Se a simulação termina em um estado de aceitação, aceite. Caso contrário, rejeite."</li>
        </ol>
      </td>
    </tr>
  </tbody>
</table>
