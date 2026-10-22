# ServeRest API — Projeto de Testes com Postman

Projeto de portfólio de QA focado em testes funcionais de uma API REST que simula operações de um e-commerce. Os testes foram executados no Postman e documentados com casos de teste, regras de negócio, rastreabilidade, registro de bugs e evidências.

## Objetivo

Praticar o planejamento e a execução de testes de API, validar respostas HTTP e regras de negócio, registrar divergências entre o comportamento observado e o Swagger e organizar evidências de forma rastreável.

## Escopo

- **Login:** autenticação válida/inválida e validação de campos.
- **Usuários:** listagem, cadastro, busca, edição, exclusão e permissões.
- **Produtos:** listagem, cadastro, edição, exclusão e restrições relacionadas a carrinhos.
- **Carrinhos:** criação, limite de carrinho por usuário, estoque, conclusão e cancelamento de compra.

## Ferramentas e ambiente

- Postman
- ServeRest API — `https://serverest.dev`
- Swagger de referência: <https://serverest.dev/swagger.json?lang=pt-BR>

## Resultado registrado

| Indicador | Resultado |
|---|---:|
| Casos executados | 32 |
| Passaram | 30 |
| Falharam | 2 |
| Não executados | 0 |
| Bugs registrados | 2 |

As duas falhas registradas foram divergências entre a resposta da API e a documentação Swagger: o nome de um campo retornado ao excluir produto associado a carrinho (BUG-001) e a mensagem retornada ao cancelar uma compra (BUG-002). No caso do cancelamento, o carrinho foi excluído e o estoque foi devolvido corretamente; a falha foi na comparação textual da mensagem.

## Estrutura de evidências

```text
EVIDENCIAS/
└── RUN/
    ├── 00 - Preparação/
    ├── 01 - Login/
    ├── 02 - Usuários/
    ├── 03 - Produtos/
    └── 04 - Carrinhos/
```

As pastas guardam evidências da preparação e das execuções por módulo. Os prints gerais das Runs ajudam a visualizar o conjunto de resultados; os prints individuais documentam os detalhes dos bugs. Os nomes exatos dos arquivos devem ser consultados no repositório.

## Documentação

- `01_Plano_de_Testes_ServeRest.docx` — objetivo, escopo, estratégia, critérios e resumo da execução.
- `02_Regras_de_Negocio_ServeRest.docx` — regras RN-01 a RN-14 e indicação da fonte.
- `03_Registro_de_Bugs_e_Observacoes.docx` — defeitos e observações identificados.
- `04_Matriz_de_Rastreabilidade_ServeRest.xlsx` — relação resumida entre regras, casos e bugs.
- `Casos_de_Teste_ServeRest_API.docx` — casos detalhados, passos e resultados observados.

## Principais aprendizados

- Construção e execução de cenários positivos, negativos e exploratórios.
- Validação de status HTTP, corpo JSON, mensagens e token de autenticação.
- Verificação de regras de negócio e efeitos colaterais, como atualização de estoque.
- Registro de bugs com caso relacionado, severidade e evidência.
- Rastreabilidade entre regras de negócio, casos de teste e defeitos.
- Identificação de lacunas entre a documentação da API e o comportamento observado.

## Observações e limitações

A ServeRest é um serviço público de estudo e pode ser compartilhado com outros usuários; os dados devem ser únicos e os resultados podem variar. A observação sobre retorno do campo `password` em endpoints de usuários foi registrada como ponto de atenção, não como conclusão de uma auditoria formal de segurança.

Este projeto demonstra prática de QA e não representa certificação completa da API nem garantia de ausência de defeitos.

## Responsável

Yan Vieira — Projeto de estudo para portfólio de QA.
