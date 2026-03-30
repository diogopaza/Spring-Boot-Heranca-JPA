🧪 💼 TESTE TÉCNICO — Spring Boot + Herança JPA
🕒 Prazo

👉 2 dias (48 horas)
Se quiser simular mais pressão: 1 dia (24h)

🎯 Objetivo

Construir uma API REST usando Spring Boot que implemente herança com:

@Inheritance(strategy = InheritanceType.SINGLE_TABLE)

E demonstre claramente:

Uso correto de herança
Persistência no banco
Estrutura da tabela
Polimorfismo funcionando
📦 Escopo do Projeto
🧾 Domínio: Sistema de Pagamentos

Você deve implementar:

🔹 Classe abstrata
Pagamento
🔹 Subclasses obrigatórias
CartaoCredito
Boleto
Pix
🧱 Requisitos Técnicos
✅ 1. Entidades (OBRIGATÓRIO)

Usar:

@Inheritance(strategy = InheritanceType.SINGLE_TABLE)

Usar:

@DiscriminatorColumn
Cada classe filha deve ter @DiscriminatorValue
✅ 2. Banco de dados

Pode usar:

H2 (mais rápido)
ou PostgreSQL (melhor ainda 💪)
✅ 3. API REST
📌 Endpoints obrigatórios:
➤ Criar pagamentos
POST /pagamentos/cartao
POST /pagamentos/boleto
POST /pagamentos/pix
➤ Listar todos
GET /pagamentos

👉 Deve retornar lista com tipos diferentes corretamente

➤ Buscar por ID
GET /pagamentos/{id}
✅ 4. JSON de entrada (exemplo)
Cartão:
{
  "valor": 150.0,
  "numeroCartao": "1234",
  "nomeTitular": "Joao"
}
Pix:
{
  "valor": 200.0,
  "chavePix": "email@teste.com"
}
🔥 Requisito IMPORTANTE (o que diferencia quem sabe 👀)
✅ 5. Mostrar como fica no banco

Você DEVE entregar:

👉 Print OU descrição da tabela gerada

Exemplo esperado:

id	valor	tipo_pagamento	numero_cartao	chave_pix
✅ 6. Demonstrar polimorfismo

No GET /pagamentos, deve retornar algo como:

[
  {
    "id": 1,
    "valor": 100,
    "numeroCartao": "1234"
  },
  {
    "id": 2,
    "valor": 200,
    "chavePix": "abc@pix"
  }
]

👉 Ou seja: cada tipo com seus campos

💥 EXTRA (DIFERENCIAL FORTE)

Se quiser subir MUITO o nível:

⭐ Endpoint único
POST /pagamentos

Com:

{
  "tipo": "PIX",
  "valor": 100,
  "chavePix": "teste@email.com"
}

👉 Você decide qual classe instanciar

⭐ Tratamento de erro
Tipo inválido
Campos obrigatórios faltando
⭐ Teste unitário (muito valorizado)
Testar criação de cada tipo
Testar persistência
📁 Entregáveis

Você deve entregar:

✅ Código fonte
Projeto Spring Boot completo
Pode ser zip ou GitHub
✅ README.md contendo:

Explique:

Como rodar o projeto
Qual banco usou
Como testar endpoints
Explicação rápida de:
SINGLE_TABLE
Como ficou a tabela
✅ Evidência do banco
Print da tabela
OU
Script SQL gerado
🧠 Critérios de Avaliação
Critério	Peso
Uso correto de herança	⭐⭐⭐⭐⭐
Estrutura da tabela	⭐⭐⭐⭐⭐
Clareza do código	⭐⭐⭐⭐
API funcionando	⭐⭐⭐⭐
Polimorfismo correto	⭐⭐⭐⭐⭐
Extras (endpoint único/teste)	⭐⭐⭐⭐⭐
⚠️ Erros que eliminam candidato

❌ Não usar SINGLE_TABLE
❌ Criar tabelas separadas
❌ Não usar @Discriminator
❌ Retornar tudo como objeto genérico sem polimorfismo
❌ Código sem rodar

🧩 Dicas (nível entrevista)
Use abstract class na base
Use @JsonTypeInfo se tiver problema no retorno JSON
Observe os campos NULL no banco
Teste no Postman ou Insomnia
🚀 Missão

Se você fizer isso direito, você vai entender:

Herança no JPA (de verdade)
Como ORM funciona por baixo
Como banco e Java se conectam
💬 Quando terminar

Me manda:

Código
Ou prints
Ou dúvidas

Que eu corrijo como se fosse um avaliador técnico 👀🔥
