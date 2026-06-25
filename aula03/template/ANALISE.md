# Análise — as 3 responsabilidades da classe `Academia` (v1.0)

**Sua tarefa (Parte 2 da atividade, 0,3):** responder com **suas palavras**
(2–4 frases por item), olhando o arquivo `academia.py` da pasta da aula.
Substitua cada `...` pela sua resposta.

---

## 1. Quais são as 3 responsabilidades grudadas na classe `Academia`?
Escreva no formato "a classe faz **X** e **Y** e **Z**":

> A classe Academia faz três coisas: calcula o valor do plano e a contagem de check-ins (regra de negócio) e lê/exibe os dados no terminal (tela) e envia mensagens via WhatsApp para o aluno (notificação).

## 2. Aponte, no código, **uma linha** de cada responsabilidade
(diga o número da linha e cole o trecho)

- **Regra de negócio** (cálculo / contagem): linha 53 — `aluno["checkins"] += 1`
- **Tela** (interface com o usuário): linha 16 — `nome = input("Nome do aluno: ")`
- **Notificação** (aviso ao aluno): linha 36 — `print(f"[WhatsApp para {nome}] Bem-vindo(a) à FitPará! Mensalidade: R${valor:.2f}.")`

## 3. Como o SRP separa essas responsabilidades?
Diga **em qual componente** cada responsabilidade passa a morar:

> A regra de negócio passa a morar na classe `AcademiaService` (em `servico/academia_service.py`), a tela passa a morar no componente de interface gráfica ou terminal (como `apresentacao/cli.py`) e a notificação passa a morar na classe `Notificador` (em `notificacao/notificador.py` ou `notificador.py`).

## 4. Por que ficou melhor? Cite **um** RNF
(manutenibilidade, testabilidade **ou** extensibilidade — veja `docs/requisitos.md`)
e explique em 1–2 frases:

> **Manutenibilidade**: ao isolarmos a notificação, se decidirmos mudar o canal de comunicação (por exemplo, de WhatsApp para E-mail ou SMS), alteramos apenas o arquivo do `Notificador`, sem o risco de quebrar as regras de matrícula ou check-in.
