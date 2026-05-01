# Aula-03-ES

Parte 1

Requisitos Funcionais (RF)

- RF01: O sistema deve cadastrar treinos dos alunos

- RF02: O sistema deve validar os dados do exercício antes de registrar

- RF03: O sistema deve armazenar o histórico de treinos do aluno

Requisitos Não Funcionais (RNF)

- RNF01: O sistema deve registrar o treino em menos de 200ms

- RNF02: O sistema deve garantir disponibilidade de 99% ao mês

- RNF03: O sistema deve proteger os dados dos usuários com criptografia

Parte 2

import time

print("🏋️ GymTrack — Validador de Treino")
print("=" * 40)

# --- DADOS DO TREINO (mude os valores para testar!) ---
exercicio = "Supino Reto"
peso_kg   = 80
repeticoes = 10

# -------------------------------------------------------
# RF01 — O sistema deve validar o nome do exercício
# (não pode ser vazio)
# -------------------------------------------------------
if exercicio != "":
    print(f"✅ [RF01] Exercício válido: {exercicio}")
else:
    print("❌ [RF01] Nome do exercício inválido!")

# -------------------------------------------------------
# RF02 — O peso deve estar entre 1 e 300 kg
# -------------------------------------------------------
if 1 <= peso_kg <= 300:
    print(f"✅ [RF02] Peso válido: {peso_kg}kg")
else:
    print("❌ [RF02] Peso inválido! Deve estar entre 1 e 300kg")

# -------------------------------------------------------
# RF03 — As repetições devem estar entre 1 e 50
# -------------------------------------------------------
if 1 <= repeticoes <= 50:
    print(f"✅ [RF03] Repetições válidas: {repeticoes}")
else:
    print("❌ [RF03] Número de repetições inválido! Deve estar entre 1 e 50")

# -------------------------------------------------------
# RNF01 — O registro deve ocorrer em menos de 200ms
# -------------------------------------------------------
inicio = time.time()

# Simula o registro no banco de dados
time.sleep(0.05)

print(f"✅ Série registrada: {exercicio} | {peso_kg}kg x {repeticoes} reps")

fim = time.time()
tempo_ms = (fim - inicio) * 1000

if tempo_ms < 200:
    print(f"✅ [RNF01] Tempo de registro: {tempo_ms:.0f}ms ← dentro do limite!")
else:
    print(f"❌ [RNF01] Lento demais: {tempo_ms:.0f}ms ← limite é 200ms")

# REFLEXÃO:
1. Qual a diferença entre RF e RNF que você percebeu na prática?
Requisitos Funcionais (RF) especificam as funcionalidades do sistema,
ou seja, descrevem os serviços, comportamentos e regras de negócio
que o software deve implementar. Já os Requisitos Não Funcionais (RNF)
definem atributos de qualidade e restrições do sistema, como desempenho,
segurança, confiabilidade e usabilidade, estabelecendo critérios mensuráveis
para avaliar se o sistema atende aos padrões esperados.

2. O que aconteceria se esquecêssemos o RNF de performance?
A ausência de um RNF de desempenho poderia resultar em um sistema
funcionalmente correto, porém ineficiente. Isso comprometeria a
experiência do usuário, reduziria a escalabilidade da aplicação
e poderia gerar impactos negativos como insatisfação dos clientes
e perda de competitividade no mercado.

3. Cite 1 RNF que o GymTrack deveria ter mas que você não implementou
O sistema deve garantir alta disponibilidade (por exemplo, 99% de uptime mensal),
assegurando que os usuários possam registrar e consultar treinos
mesmo em horários de pico, minimizando indisponibilidades.
