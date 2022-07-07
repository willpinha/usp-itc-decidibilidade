# USP - ITC - Decidibilidade

> Catálogo de problemas decidíveis e indecidíveis para a matéria Introdução à Teoria da Computação

![semestre](https://img.shields.io/badge/semestre-5sem--2022-green)
![matéria](https://img.shields.io/badge/mat%C3%A9ria-ACH2043--ITC-blue)

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
      <td>Vacuidade de um AFD</td>
      <td>$V_{AFD} = \{ (A) | A$ é um $AFD$ e $L(A) = \emptyset \}$</td>
      <td>$M_{V_{AFD}} =$ "Sobre a entrada $(A)$, onde $A$ é um $AFD$:
        <ol>
          <li>Marque o estado inicial $A$</li>
          <li>Repita até que nenhum estado novo venha a ser marcado:
            <ol>
              <li>Marque qualquer estado que tenha uma transição chegando nele a partir de qualquer estado que já tenha sido marcado</li>
            </ol>
          </li>
          <li>Se nenhum estado de aceitação estiver marcado, aceite. Caso contrário, rejeite"</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td>Equivalência entre $AFD$'s</td>
      <td>$EQ_{AFD} = \{ (A,B) | A$ e $B$ são $AFD$'s e $L(A) = L(B) \}$</td>
      <td>$M_{EQ_{AFD}} =$ "Sobre a entrada $(A,B)$, sendo $A$ e $B$ $AFD$'s:
        <ol>
          <li>Construa um $AFD$ $C$ tal que $L(C) = (L(A) \cap \overline{L(B)}) \cup (\overline{L(A)} \cap L(B))$</li>
          <li>Rode a entrada $(C)$ sobre a máquina $M_{V_{AFD}}$</li>
          <li>Se $M_{V_{AFD}}$ aceitar, aceite. Caso contrário, rejeite"</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td>Geração de uma cadeia por uma GLC</td>
      <td>$A_{GLC} = \{ (G,w) | G$ é uma $GLC$ que gera a cadeia $w \}$</td>
      <td>$M_{A_{GLC}} =$ "Sobre a entrada $(G,w)$, onde $G$ é uma $GLC$ e $w$ é uma cadeia:
        <ol>
          <li>Converta $G$ para uma gramática $G'$ equivalente na forma normal de Chomsky</li>
          <li>Liste todas as derivações com $2n - 1$ passos, onde $n$ é o comprimento de $w$, exceto se $n = 0$. Nesse último caso, liste todas as
            derivações com 1 passo</li>
          <li>Se alguma dessas derivações gera $w$, aceite. Caso contrário, rejeite"</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td>Vacuidade de uma GLC</td>
      <td>$V_{GLC} = \{ (G) | G$ é uma $GLC$ e $L(G) = \emptyset \}$</td>
      <td>$M_{V_{GLC}} =$ "Sobre a entrada $(G)$, onde $G$ é uma $GLC$:
        <ol>
          <li>Marque todos os números terminais em $G$</li>
          <li>Repita até que nenhuma variável venha a ser marcada:
            <ol>
              <li>Marque qualquer variável $A$ onde $G$ tem uma regra $A \rightarrow U_{1}U_{2}...U_{k}$ e cada símbolo $U_{1}...U_{k}$ já tenha sido  
                marcado</li>
            </ol>
          </li>
          <li>Se a variável inicial não está marcada, aceite. Caso contrário, rejeite"</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td>Equivalência entre $AFD$ e expressão regular</td>
      <td>$EQ_{AFD,EXP} = \{ (A,E) | A$ é um $AFD$, $E$ é uma expressão regular e $L(A) = L(E) \}$</td>
      <td>$M_{EQ_{AFD,EXP}} =$ "Sobre a entrada $(A,E)$, onde $A$ é um $AFD$ e $E$ é uma expressão regular:
        <ol>
          <li>Converta a expressão regular $E$ em um $AFD$ $E'$ equivalente</li>
          <li>Rode a entrada $(A,E')$ sobre a máquina $EQ_{AFD}$</li>
          <li>Se $EQ_{AFD}$ aceitar, aceite. Caso contrário, rejeite"</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td>Aceitação de todas as cadeias por um $AFD$</td>
      <td>$TODAS_{AFD} = \{ (A) | A$ é um $AFD$ e $L(A) = \Sigma^* \}$</td>
      <td>$M_{TODAS_{AFD}} =$ "Sobre a entrada $(A)$ sendo $A$ um $AFD$:
        <ol>
          <li>Se todos os estados alcançáveis de $A$ forem finais, aceite. Caso contrário, rejeite"</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td>Linguagem de expressão regular contida em linguagem de outra expressão regular</td>
      <td>$C_{EXP/EXP} = \{ (R,S) | R$ e $S$ são expressões regulares e $L(R) \subseteq L(S) \}$</td>
      <td>$M_{C_{EXP/EXP}} =$ "Sobre a entrada $(R,S)$, onde $R$ e $S$ são expressões regulares:
        <ol>
          <li>Sendo $R^c$ a expressão regular que gera o complemento de $L(R)$, e sabendo que expressões regulares são fechadas sobre a operação
          de interseção, rode a entrada $(R^c \cap L(S))$ sobre a máquina $V_{EXP}$</li>
          <li>Se $V_{EXP}$ aceitar, aceite. Caso contrário, rejeite"</li>
        </ol>
      </td>
    </tr>
  </tbody>
</table>

## Problemas indecidíveis
