# TechOS Core - Documentação

## 1. USER STORIES (INVEST)
- **US01:** "Como técnico, quero abrir uma Ordem de Serviço para registrar um conserto."
  - C.A.01: Deve validar o ID do cliente.
  - C.A.02: O status inicial deve ser sempre 'ABERTA'.
- **US02:** "Como cliente, quero visualizar o status do meu equipamento."

## 2. REQUISITOS NÃO-FUNCIONAIS (RNF)
- **RNF01 (Segurança):** Sanitização de inputs contra XSS/OWASP no cadastro.
- **RNF02 (Desempenho):** Tempo de resposta na criação de chamados < 2s.

## 3. DIAGRAMA DE CLASSES
+-----------------------------------+
|          <<Abstrata>>             |
|             Usuario               |
+-----------------------------------+
| - id: int                         |
| - nome: string                    |
| - email: string                   |
+-----------------------------------+
| + getId()                         |
| + getNome()                       |
| + getEmail()                      |
+-----------------------------------+
                 ^
                 | (Herança)
      +----------+----------+
      |                     |
+---------------+     +---------------+
|    Cliente    |     |    Tecnico    |
+---------------+     +---------------+
| - telefone    |     | - especialid. |
+---------------+     +---------------+

+-----------------------------------+
|           OrdemServico            |
+-----------------------------------+
| - id: int                         |
| - cliente: string                 |
| - tecnico: string                 |
| - status: string                  |
| - descricao: string               |
+-----------------------------------+# techos-core-maria-luiza
