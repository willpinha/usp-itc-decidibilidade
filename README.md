# USP - ITC - Decidibilidade

> Catálogo de problemas decidíveis e indecidíveis para a matéria Introdução à Teoria da Computação

![Semestre](https://img.shields.io/badge/Semestre-5sem--2022-green)
![Matéria](https://img.shields.io/badge/Mat%C3%A9ria-ACH2043--ITC-blue)

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
    <tr>
      <td>Aceitação de uma cadeia por um AFN</td>
      <td>$A_{AFN} = \{ (B,w) | B$ é um $AFN$ que aceita a cadeia $w \}$</td>
      <td>$M_{A_{AFN}} =$ "Sobre a entrada $(B,w)$, onde $B$ é um $AFN$ e $w$ é uma cadeia:
        <ol>
          <li>Converta $B$ para um $AFD$ $B'$ equivalente</td>
          <li>Rode a entrada $(B',w)$ sobre a máquina $M_{A_{AFD}}$</li>
          <li>Se $M_{A_{AFD}}$ aceitar, aceite. Caso contrário, rejeite."</li>
        </ol>
      </td>
    </tr>
  </tbody>
</table>
