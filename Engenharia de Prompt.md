Modelos de Processamento de Linguagem Natural (NLP) como ChatGPT, Gemini, LLaMa e Copilot recebem instruções em forma de texto, que nesse contexto é denominado **prompt**.
A equipe de pesquisa da Google descobriu que a qualidade das respostas produzidas pelo LLM é dependente da qualidade dos prompts, e publicaram em [um artigo](https://arxiv.org/abs/2201.11903), onde detalham uma técnica de engenharia de prompt usada para aprimorar as respostas errôneas produzidas pelo GPT-3.

Um problema que usuários de LLMs como o ChatGPT rapidamente percebem é que o modelo pode responder a uma pergunta com informações falsas, por vezes completamente sem base na realidade, e faz isso com tom de confiança.
O problema aqui é o risco de desinformação, o que reduz a confiabilidade desses modelos que podem ser tão úteis.

Mas há como diminuir a frequência dos erros cometidos pelos modelos, construindo prompts melhores e mais diretos. Isso é a **Engenharia de Prompt**.
Adiante, listo técnicas de engenharia de prompt, mas vale lembrar que essas não são todas as técnicas que existem.
## Técnicas de prompting
### Zero-shot
A técnica zero-shot (nenhum exemplo, em tradução livre) funciona bem quando a intenção é avaliar a capacidade de um modelo de produzir boas respostas sem qualquer instrução adicional. Por exemplo:
###### Figura 1
![[Exemplo de Zero Shot Prompting - ChatGPT 4o mini.PNG]]
### Few-shot
Em ocasiões onde o modelo se mostra incapaz de produzir uma boa resposta, pode ser útil empregar a técnica do Few-shot (alguns exemplos, em tradução livre). Um exemplo de resposta ruim:
###### Figura 2
![[Exemplo de resposta inválida com Zero Shot Prompting - ChatGPT 4o mini.PNG]]
A resposta é absurda. Santa Catarina não faz fronteira com o Espírito Santo, assim como Minas Gerais não está mais a oeste em relação a Santa Catarina.
Apesar desse erro, o resultado melhora se dermos alguns exemplos de como resolver esse problema de antemão.
### Chain-of-thought
### Zero-shot chain-of-thought
### Least-to-Most
### Self-consistency
### Selection-Inference
### Maieutic
### ReAct
### ART
## Referências
* https://www.alura.com.br/artigos/engenharia-prompt?srsltid=AfmBOoq6Y3671MEr9cr5wSJuNGm5NyoSf6oMBQbw1lm9yHCxLIfiv4p3
* https://arxiv.org/abs/2201.11903#
* https://arxiv.org/abs/2205.11916#