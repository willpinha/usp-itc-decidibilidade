# USP - ITC - Decidibilidade

> Catálogo de problemas decidíveis e indecidíveis para a matéria Introdução à Teoria da Computação

O catálogo contém três colunas: **Problema**, **Linguagem** e **Máquina de Turing**. O problema contém a descrição de um determinado problema que deve ser 
decidível ou indecidível. A linguagem contém uma especificação desse problema na forma de um conjunto. A máquina de Turing contém a resolução desse 
problema utilizando o modelo descritivo de uma máquina de Turing.

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
