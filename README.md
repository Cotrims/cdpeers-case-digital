# Case OrbitShop — Peers Digital Consulting (etapa individual)

## O enunciado

A OrbitShop é uma plataforma de e-commerce (B2C e B2B) que está fechando uma rodada Series C. Ao analisar o data room, o fundo investidor encontrou dois números contraditórios sobre cancelamento e pausou a rodada:

- **Camila (Head de Growth):** "o cancelamento subiu 40% em relação ao ano passado";
- **Rogério (CFO):** "o cancelamento caiu de 18% para 16%".

A CEO pediu à Peers uma explicação sustentada pelos dados. A base `Base_Dados_OrbitShop.xlsx` tem seis tabelas (Clientes, Produtos, Pedidos, Itens_Pedido, Tickets_Suporte e Avaliacoes), cobre jan/2023 a dez/2024 e vem sem limpeza nenhuma.

A entrega pede:
1. um **memo de 1 página** (até 400 palavras), com a resposta da Q1 no topo e uma seção "Uso de IA";
2. um **notebook que reproduza os números**, com README.

As perguntas:
- **Q1:** três perguntas para a Camila e o Rogério, feitas antes de olhar os dados;
- **Q2–Q5:** status dos pedidos, categorias que mais vendem, cancelamento por canal de aquisição e sazonalidade;
- **Q6–Q9:** conciliação de valores, fornecedores × chamados, uma ação recomendada e o que os dados não respondem.

## Arquivos

| Arquivo | O que é |
|---|---|
| `memo.md` | Memo para a CEO |
| `main.ipynb` | Notebook (Colab/Jupyter) com toda a análise |
| `Base_Dados_OrbitShop.xlsx` | Base original, sem alterações |
| `Case_OrbitShop_Individual_v2.pptx` | Enunciado do case |
| `requirements.txt` | Dependências Python |

## O que há no notebook

0. **Carga e checagem:** leitura das seis abas, contagem de nulos, checagem de chaves órfãs e preenchimento dos 301 descontos vazios.
1. **Q1:** as três perguntas, respondidas antes de olhar a base.
2. **Q2:** tabela e gráfico de status por ano, mais um teste das duas frases (Camila e Rogério) com definições diferentes de taxa.
3. **Q3:** receita × unidades por categoria.
4. **Q4:** taxa de cancelamento e ticket médio por canal de aquisição; paid search cancela 30,7%, contra ~12% nos demais canais.
5. **Q5:** pedidos por mês e análise do pico de nov/2023 (4× o normal).
6. **Q6:** `valor_total` × soma dos itens (não conciliam) e qual dos dois levar ao conselho.
7. **Q7:** nota média por fornecedor (DeltaFornece ME é a pior) e chamados por 100 pedidos.
8. **Q8:** impacto estimado de trazer paid search ao nível dos outros canais.
9. **Q9:** o que ficou sem resposta e o que pedir ao time de dados.
10. **Registro de uso de IA.**

Cada questão tem o código (pandas), uma tabela ou gráfico e um bloco **Resposta** com a interpretação.

## Como rodar

**Google Colab:** abra o `main.ipynb`, faça upload do `Base_Dados_OrbitShop.xlsx` na sessão e rode tudo (*Ambiente de execução → Executar tudo*).

**Local:**
```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook main.ipynb
```
