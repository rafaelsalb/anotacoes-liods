## O processo de anonimização
Anonimizar um conjunto de dados deve manter as propriedades estatísticas originais do conjunto. Contudo, como o processo costuma adicionar ruído aos conjuntos, é esperado que as propriedades estatísticas sejam alteradas. Por conta disso, pode ser que o grau de utilidade do conjunto seja reduzido, fazendo necessário definir um balanço entre o risco de reidentificação dos dados e sua utilidade, como demonstrado na [[#Figura 1]].
###### Figura 1
![[Anonimização X Utilidade.excalidraw]]
Uma prática importante nessa etapa do processo é documentar as propriedades estatísticas do conjunto de dados.
### Risco de reidentificação
O processo de anonimização não pode produzir um resultado perfeitamente anonimizado, em que nenhum dos dados pode ser reidentificado. Portanto, o risco de reidentificação por meio de um ataque de reidentificação é sempre real.
### Tipos de ataque de reidentificação
Existem dois tipos de ataque de reidentificação comuns:
1. **Ataque do promotor**: quando o atacante conhece um indivíduo presente no conjunto de dados, e a intenção é encontrar o registro referente a ele;
2. **Ataque do jornalista**: quando o atacante não conhece nenhum indivíduo presente no conjunto de dados, e visa reidentificar qualquer quantidade de registros.
O Risco de Reidentificação deve ser medido como uma probabilidade.
### Primeira etapa: determinar o Risco de Reidentificação Aceitável
Uma etapa muito importante do processo de anonimização de dados é determinar o RRA (Risco de Reidentificação Aceitável).
A ideia aqui é estipular um limite superior, significando que um conjunto de dados com risco de reidentificação superior ao RRA definido será considerado como não anonimizado.
### Segunda etapa: aplicar as técnicas de anonimização
Nessa etapa, são aplicadas as técnicas de anonimização no conjunto de dados escolhido.
### Terceira etapa: determinar o Risco de Reidentificação Mensurado
Na penúltima etapa, o RRM (Risco de Reidentificação Mensurável) é calculado, a fim de classificar a anonimização como bem-sucedida ou não. Para isso, compara-se a probabilidade representada pelo RRM com o RRA.
Caso o RRM seja maior que o RRA, a anonimização foi mal sucedida, e o processo deve partir do início.
#### Medindo o RRM
Tomemos como exemplo a [[#^374a0d |Figura 2]]
###### Figura 2
^374a0d

![[Exemplo Anonimização.excalidraw]]
Esse é um conjunto de dados que mostra informações sobre os estudantes de uma universidade qualquer.

É importante conhecer o conceito de **Equivalência de Classe**.
> [!info] Equivalência de Classe
> Duas classes são consideradas equivalentes quando compartilham os mesmos valores em determinado campo.

Dividindo o nosso exemplo por equivalência de classes, temos:
###### Figura 3
![[Equivalência de classes 1.excalidraw]]
Aqui, a equivalência de classes é igual a 3.
###### Figura 4
![[Equivalência de classes 2.excalidraw]]
Equivalência de classes = 1
###### Figura 5
![[Equivalência de classes 3.excalidraw]]
Equivalência de classes = 1

Em geral, quanto menor for o grau de equivalência de classes, maior é a chance de o dado ser único (e portanto, identificável), e maior é o risco de reidentificação. Isso fica mais claro quando expressamos as probabilidades numéricas:

| Curso                 | Risco de reidentificação |
| --------------------- | ------------------------ |
| Ciência da Computação | 33%                      |
| Design                | 100%                     |
| Jornalismo            | 100%                     |
| TODOS                 | 77.66%                   |
O RRM é, então:
$$Risco\ de\ Reidentificação\ Mensurado=V_c\ * \theta$$
> **θ**: valor geral da métrica contextual.
> **Vc**: fator de ponderação das variáveis contextuais. Pode existir ou não (assumindo o valor de 1, nesse caso).

No caso de bases de dados públicas ou compartilhadas, é boa prática considerar o risco maior do que realmente é, como medida de segurança. O motivo disso é que um atacante teria acesso aos dados e poderia executar diversos procedimentos para reidentificar registros.
## Fontes
* https://www.gov.br/anpd/pt-br/documentos-e-publicacoes/documentos-de-publicacoes/estudo_tecnico_sobre_anonimizacao_de_dados_na_lgpd_uma_visao_de_processo_baseado_em_risco_e_tecnicas_computacionais.pdf