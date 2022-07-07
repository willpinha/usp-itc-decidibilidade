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
          <li>Se a simulação termina em um estado de aceitação, aceite. Caso contrário, rejeite"</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td>Aceitação de uma cadeia por um AFN</td>
      <td>$A_{AFN} = \{ (B,w) | B$ é um $AFN$ que aceita a cadeia $w \}$</td>
      <td>$M_{A_{AFN}} =$ "Sobre a entrada $(B,w)$, onde $B$ é um $AFN$ e $w$ é uma cadeia:
        <ol>
          <li>Converta $B$ para um $AFD$ $B'$ equivalente</li>
          <li>Rode a entrada $(B',w)$ sobre a máquina $M_{A_{AFD}}$</li>
          <li>Se $M_{A_{AFD}}$ aceitar, aceite. Caso contrário, rejeite"</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td>Geração de uma cadeia por uma expressão regular</td>
      <td>$A_{EXP} = \{ (R,w) | R$ é uma expressão regular que gera a cadeia $w \}$</td>
      <td>$M_{A_{EXP}} =$ "Sobre a entrada $(R,w)$, onde $R$ é uma expressão regular e $w$ é uma cadeia:
        <ol>
          <li>Converta a expressão regular $R$ para uma $AFN$ $A$ equivalente</li>
          <li>Rode a entrada $(A,w)$ sobre a máquina $M_{A_{AFN}}$</li>
          <li>Se $M_{A_{AFN}}$ aceitar, aceite. Caso contrário, rejeite"</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td>Equivalência de $AFD$'s</td>
      <td>$EQ_{AFD} = \{ (A,B) | A$ e $B$ são $AFD$'s e $L(A) = L(B) \}$</td>
      <td>$M_{EQ_{AFD}} =$ "Sobre a entrada $(A,B)$, sendo $A$ e $B$ $AFD$'s:
        <ol>
          <li>Construa um $AFD$ $C$ tal que $L(C) = (L(A) \cap \overline{L(B)}) \cup (\overline{L(A)} \cap L(B))$</li>
        </ol>
      </td>
    </tr>
  </tbody>
</table>
