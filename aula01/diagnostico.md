# Diagnóstico do Sistema de Empréstimo — Aluno

## Problema 1
- O que a documentação diz: A regra RN02 em requisitos.md exige que o prazo mínimo de empréstimo seja de 1 dia.
- O que o código faz: O método `registrar()` não faz a validação da quantidade de dias.
- Por que é um problema: Permite criar um empréstimo inválido com prazo 0 ou negativo sem aviso, comprometendo a integridade dos dados.
- (Já documentado? não)

## Problema 2
- O que a documentação diz: O passo 4 do UC03 em casos_de_uso.md orienta a exibir a mensagem "Nenhum empréstimo em atraso" quando não há atrasos.
- O que o código faz: O método `listar_atrasados()` não imprime nada quando a lista está vazia.
- Por que é um problema: A falta de feedback visual deixa o usuário em dúvida se o sistema processou o pedido ou se travou.
- (Já documentado? não)

## Problema 3
- O que a documentação diz: A regra RI02 em requisitos.md determina que toda operação bem-sucedida deve exibir confirmação explícita.
- O que o código faz: O método `registrar()` não mostra uma mensagem clara de "empréstimo registrado".
- Por que é um problema: O usuário não tem certeza se a ação foi concluída com sucesso e pode acabar efetuando o registro novamente.
- (Já documentado? não)

## Problema 4
- O que a documentação diz: A regra RI03 em requisitos.md especifica que toda operação inválida deve exibir mensagem de erro descritiva.
- O que o código faz: O menu no método `main()` não trata opções desconhecidas (ex: ao digitar 9, o sistema não mostra erro nenhum, só repete o menu).
- Por que é um problema: Fere a usabilidade, pois o usuário pode digitar incorretamente e não ser guiado pelo sistema sobre o erro cometido.
- (Já documentado? não)

## Problema 5
- O que a documentação diz: A Tabela de Dívida Técnica (DT04) documenta que o cálculo de multa está copiado em dois métodos.
- O que o código faz: O mesmo bloco `if/elif` que calcula a multa por tipo de equipamento aparece nos métodos `devolver()` e `listar_atrasados()`.
- Por que é um problema: Alterar o valor de uma multa obriga o desenvolvedor a alterar em dois lugares, violando o princípio DRY (Don't Repeat Yourself) e aumentando a chance de inconsistências.
- (Já documentado? sim)
