# Exercícios Práticos: Diagramas de Atividade e Sequência UML

## 📚 Instruções Gerais

Os exercícios estão organizados em três níveis de dificuldade:

- **🟢 Iniciante**: Conceitos básicos e interpretação simples
- **🟡 Intermediário**: Aplicação prática com maior complexidade  
- **🔴 Avançado**: Modelagem completa e análise crítica

---

## 🟢 **NÍVEL INICIANTE**

### **Exercício 1: Interpretando um Diagrama de Atividade - Sistema de Login**

Observe o diagrama de atividade abaixo que representa o processo de login em uma rede social:

```
[●] Início
  ↓
[Inserir nome de usuário]
  ↓
[Inserir senha]
  ↓
{◊} Dados corretos?
  ↓ [Sim]        ↓ [Não]
[Entrar no      [Exibir mensagem
 sistema]        de erro]
  ↓                ↓
[Carregar        [Voltar para
 perfil]          tela de login]
  ↓                ↓
[◉] Fim    ←──────────┘
```

**Questões:**

1. **Identifique os símbolos**: Quais são os 5 tipos de símbolos utilizados neste diagrama e o que cada um representa?

2. **Fluxo alternativo**: O que acontece quando o usuário insere dados incorretos? Descreva o caminho completo.

3. **Melhoria do processo**: Sugira uma melhoria para este processo (ex: limite de tentativas, recuperação de senha, etc.).

---

### **Exercício 2: Criando um Diagrama de Sequência Simples - Pedido em Lanchonete**

Você precisa criar um diagrama de sequência para o seguinte cenário:

**Cenário**: João vai a uma lanchonete e faz o seguinte processo:
- João fala com o atendente
- Atendente pergunta o pedido
- João diz que quer um hambúrguer
- Atendente anota o pedido
- Atendente informa o valor (R$ 15,00)
- João paga
- Atendente entrega o pedido

**Tarefa**: Desenhe um diagrama de sequência básico identificando:
- Os dois atores (João e Atendente)
- As mensagens trocadas entre eles
- A ordem temporal das interações

---

### **Exercício 3: Análise de Símbolos UML**

Relacione cada símbolo com sua descrição correta:

**Símbolos:**
A. ◊ (Losango)
B. ● (Círculo preenchido) 
C. ◉ (Círculo com borda)
D. ▬ (Barra horizontal)
E. → (Seta sólida)

**Descrições:**
1. ( ) Nó final de atividade
2. ( ) Mensagem síncrona em diagrama de sequência  
3. ( ) Nó de decisão
4. ( ) Nó inicial
5. ( ) Nó de junção/sincronização

---

## 🟡 **NÍVEL INTERMEDIÁRIO**

### **Exercício 4: Modelando um Sistema de Biblioteca - Diagrama de Atividade**

Você é responsável por modelar o processo de empréstimo de livros em uma biblioteca escolar.

**Processo completo:**
1. Aluno procura um livro
2. Sistema verifica se o livro está disponível
3. Se disponível: verifica se aluno pode pegar emprestado (máximo 3 livros)
4. Se pode pegar: registra empréstimo e entrega livro
5. Se não pode ou livro indisponível: informa aluno e oferece reserva
6. Se aceita reserva: registra na fila de espera
7. Se não aceita: processo termina

**Tarefa**: Crie um diagrama de atividade completo incluindo:
- Nós de início e fim
- Todas as ações
- Pelo menos 2 decisões
- Fluxos alternativos
- Use condições de guarda nas saídas das decisões

---

### **Exercício 5: Sistema de Pedido Online - Diagrama de Sequência**

Modele a interação entre um Cliente, Sistema Web, Sistema de Pagamento e Estoque para um pedido online:

**Fluxo:**
1. Cliente acessa o site
2. Sistema carrega catálogo
3. Cliente escolhe produto
4. Sistema verifica estoque
5. Se disponível: Cliente prossegue para pagamento
6. Sistema Web envia dados para Sistema de Pagamento
7. Sistema de Pagamento processa e confirma
8. Sistema Web atualiza estoque
9. Sistema confirma pedido para Cliente

**Requisitos:**
- Use 4 linhas de vida (atores/objetos)
- Inclua pelo menos 8 mensagens
- Use mensagem de retorno para confirmações
- Adicione uma caixa de ativação para o processamento do pagamento

---

### **Exercício 6: Análise Crítica - Fluxo com Paralelismo**

Observe o cenário: "Preparação de uma festa de aniversário"

Algumas atividades podem ser feitas em paralelo:
- Decorar o local E preparar a comida podem acontecer ao mesmo tempo
- Convidar pessoas pode ser feito antes de tudo
- Comprar ingredientes deve acontecer antes de preparar comida
- Montar som deve ser após decorar local

**Tarefas:**
1. Identifique quais símbolos UML você usaria para representar o paralelismo
2. Desenhe um diagrama de atividade mostrando o garfo (fork) e junção (join)
3. Explique por que um fluxograma tradicional teria dificuldade em representar este cenário

---

## 🔴 **NÍVEL AVANÇADO**

### **Exercício 7: Sistema Completo - Caixa Eletrônico**

Desenvolva um diagrama de atividade completo para um sistema de caixa eletrônico com as seguintes funcionalidades:

**Fluxo Principal:**
1. Cliente insere cartão
2. Sistema valida cartão
3. Cliente digita senha (máximo 3 tentativas)
4. Sistema autentica
5. Mostra menu de opções: Saque, Consulta Saldo, Extrato
6. Cliente escolhe operação
7. Para SAQUE: verifica saldo e limite, dispensa dinheiro
8. Para CONSULTA: mostra saldo na tela  
9. Para EXTRATO: imprime últimas 10 transações
10. Pergunta se deseja nova operação
11. Finaliza e retorna cartão

**Cenários de exceção:**
- Cartão inválido → retorna cartão
- 3 senhas erradas → retém cartão
- Saldo insuficiente → exibe erro
- Sem dinheiro no caixa → exibe erro
- Problema na impressora (extrato) → oferece envio por email

**Requisitos técnicos:**
- Use partições (swimlanes) para separar ações do Cliente e do Sistema
- Inclua todos os nós de controle necessários
- Use condições de guarda detalhadas
- Represente pelo menos um loop para as tentativas de senha
- Adicione símbolos de nota para explicar regras de negócio complexas

---

### **Exercício 8: Sistema de E-commerce - Diagrama de Sequência Avançado**

Modele um sistema completo de compra online com os seguintes participantes:

**Atores/Objetos:**
- Cliente
- Interface Web  
- Controlador de Pedidos
- Sistema de Autenticação
- Base de Dados de Produtos
- Sistema de Pagamento (externo)
- Sistema de Estoque
- Sistema de Notificação

**Cenário Complexo:**
1. Cliente não logado tenta comprar
2. Sistema redireciona para login
3. Cliente faz login (autenticação)
4. Retorna para página do produto
5. Cliente adiciona ao carrinho
6. Sistema verifica estoque em tempo real
7. Cliente finaliza compra
8. Sistema calcula frete e impostos
9. Cliente confirma e vai para pagamento
10. Sistema externo processa pagamento
11. Se aprovado: reserva produto no estoque
12. Envia emails de confirmação
13. Se reprovado: libera produto e notifica erro

**Requisitos avançados:**
- Use fragmentos de sequência (alt, opt, loop)
- Inclua mensagens assíncronas para notificações
- Use notas para explicar regras de negócio
- Represente mensagens de criação e destruição de objetos temporários
- Adicione restrições temporais em pelo menos uma operação

---

### **Exercício 9: Projeto Integrado - Sistema Escolar**

**Contexto**: Você deve modelar um sistema de matrícula escolar que envolve múltiplos processos e atores.

**Parte A - Diagrama de Atividade**: Processo de matrícula anual
- Aluno solicita matrícula
- Secretaria verifica documentação
- Se documentação OK: verifica vagas na série desejada
- Se há vagas: calcula mensalidade com descontos aplicáveis
- Aluno/responsável analisa valores
- Se aceita: efetua matrícula e primeira parcela
- Sistema gera contrato e carteirinha
- Se rejeita valores: pode solicitar revisão de desconto
- Coordenação analisa caso especial
- Aprova/rejeita desconto adicional

**Parte B - Diagrama de Sequência**: Sistema de notas online
- Professor acessa sistema
- Lança notas da turma
- Sistema calcula médias automaticamente
- Sistema identifica alunos em recuperação
- Envia notificação automática para responsáveis
- Responsável acessa portal e visualiza boletim
- Pode solicitar reunião pedagógica
- Sistema agenda reunião disponível

**Requisitos Especiais:**
1. **Integração**: Os dois diagramas devem se conectar (aluno matriculado pode ter notas)
2. **Complexidade**: Use todos os conceitos aprendidos
3. **Documentação**: Adicione notas explicativas sobre regras de negócio
4. **Validação**: Revise os diagramas verificando se fazem sentido na prática

---

## 🎯 **Exercício Desafio - Análise Comparativa**

Compare as vantagens e desvantagens dos Diagramas de Atividade versus Diagramas de Sequência para os seguintes cenários. Justifique qual seria mais apropriado:

1. **Modelar o processo de matrícula em uma universidade**
2. **Documentar como objetos interagem em um jogo online**  
3. **Explicar o fluxo de aprovação de um empréstimo bancário**
4. **Mostrar a comunicação entre microserviços em uma aplicação**

Para cada cenário, responda:
- Qual diagrama é mais adequado e por quê?
- Que informações cada tipo de diagrama destacaria melhor?
- Em que situação você usaria ambos os tipos para o mesmo sistema?

---

## 📋 **Critérios de Avaliação**

### Para todos os exercícios, considere:

**Correção Técnica (40%)**
- Uso correto dos símbolos UML
- Sintaxe e notação adequadas
- Fluxos lógicos e consistentes

**Completude (30%)**
- Todos os requisitos atendidos
- Cenários alternativos considerados
- Detalhamento apropriado para o nível

**Clareza e Organização (20%)**
- Diagramas limpos e legíveis
- Nomeação clara de ações e objetos
- Layout organizado

**Criatividade e Análise Crítica (10%)**
- Soluções inovadoras para problemas
- Melhorias sugeridas nos processos
- Reflexões sobre aplicabilidade

---

*Boa sorte e lembre-se: UML é uma ferramenta para comunicar ideias. O mais importante é que seus diagramas sejam compreensíveis e úteis!* 🚀
