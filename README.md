# Aula-03-ES

EXERCÍCIO PRÁTICO — Hands-on no Google Colab / VS Code
🎯 Missão: Validador de Requisitos para um App de Academia
Você foi contratado para desenvolver o sistema GymTrack — um app para academias acompanharem treinos de alunos.
Parte 1 — Classificação (5 min)
Liste 3 RFs e 3 RNFs para o GymTrack. Use a estrutura:
RF01: O sistema deve [verbo] + [o quê]
RNF01: O sistema deve [verbo] + [como/quanto]
Parte 2 — Código Python (15 min)
Complete os trechos marcados com # SEU CÓDIGO AQUI e rode no Colab:
import time

print("🏋️ GymTrack — Validador de Treino")
print("=" * 40)

--- DADOS DO TREINO (mude os valores para testar!) ---
exercicio = "Supino Reto"
peso_kg   = 80
repeticoes = 10


RF01 — O sistema deve validar o nome do exercício
(não pode ser vazio)

SEU CÓDIGO AQUI: cheque se exercicio != ""
Dica: use  if exercicio != "":  ...


RF02 — O peso deve estar entre 1 e 300 kg

SEU CÓDIGO AQUI: cheque se peso_kg está entre 1 e 300
Dica: use  if 1 <= peso_kg <= 300:  ...

RF03 — As repetições devem estar entre 1 e 50

SEU CÓDIGO AQUI: cheque se repeticoes está entre 1 e 50

RNF01 — O registro deve ocorrer em menos de 200ms

inicio = time.time()
Simula o registro no banco de dados
time.sleep(0.05)
print(f"✅ Série registrada: {exercicio} | {peso_kg}kg x {repeticoes} reps")
fim = time.time()
tempo_ms = (fim - inicio) * 1000
if tempo_ms < 200:
    print(f"✅ [RNF01] Tempo de registro: {tempo_ms:.0f}ms ← dentro do limite!")
else:
    print(f"❌ [RNF01] Lento demais: {tempo_ms:.0f}ms ← limite é 200ms")
Output esperado (quando tudo estiver correto):
🏋️ GymTrack — Validador de Treino
========================================
✅ [RF01] Exercício válido: Supino Reto
✅ [RF02] Peso válido: 80kg
✅ [RF03] Repetições válidas: 10
✅ Série registrada: Supino Reto | 80kg x 10 reps
✅ [RNF01] Tempo de registro: 52ms ← dentro do limite!
Parte 3 — Reflexão (5 min)
Responda no código (como comentário):

REFLEXÃO:
1. Qual a diferença entre RF e RNF que você percebeu na prática?
2. O que aconteceria se esquecêssemos o RNF de performance?
3. Cite 1 RNF que o GymTrack deveria ter mas que você não implementou
