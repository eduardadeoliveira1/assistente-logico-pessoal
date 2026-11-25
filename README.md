# Assistente Lógico Pessoal

> Atividade da disciplina Linguagem de Programação e Paradigmas · UNIDAVI · 2026/2

**Aluno(a):** Eduarda de Oliveira
**Linguagem do sistema:** Python 

## O que é

Uma base de conhecimento em Prolog (`meus_dados.pl`) com fatos e regras sobre mim e um assistente em linha de comando que consulta essa base pela ponte (`prolog.py` ou `prolog.js`).

## Como executar

Requisitos: SWI-Prolog no PATH e Python.

```bash
# testar a ponte
python teste_ponte.py      
# executar o assistente
python assistente.py       
```

## Minha base

- Fatos: `eu/1`, `cursa/3`, `compromisso/3`, `sabe/2`, `gosta/2`
- Regras: `ocupado/2`, `livre/2`, `o_que_faco/3`, `pode_ensinar/1`, `dia_cheio/1` e a minha regra abaixo

## Minha regra (R6)

R6 · Posso praticar um hobby quando estou livre à noite  e tenho interesse em algum hobby.
posso_praticar_hobby(Dia, Hobby) :-
    dia(Dia),
    livre(Dia, noite),
    gosta(hobby, Hobby).

**O que ela significa:** A regra verifica em quais dias posso praticar meus hobbies durante a noite. O primeiro subobjetivo (dia(Dia)) verifica os dias cadastrados na semana. O segundo (livre(Dia, noite)) verifica se estou livre à noite, e o terceiro (gosta(hobby, Hobby)) identifica os hobbies pelos quais tenho interesse. Assim, o Prolog retorna os dias em que tenho disponibilidade para praticar meus hobbies.

## Saída real do assistente

=== Assistente pessoal de eduarda ===
1. Minhas disciplinas
2. Agenda de um dia
3. Horários livres
4. Estou livre em...?
5. Linguagens que posso ensinar
6. Meus gostos por categoria
7. Dias cheios
0. Sair
> 7

== Dias cheios (2 turnos ou mais ocupados) ==
  - segunda
  - terca
  - quarta
  - quinta
  - sexta
  - sabado

  === Assistente pessoal de eduarda ===
1. Minhas disciplinas
2. Agenda de um dia
3. Horários livres
4. Estou livre em...?
5. Linguagens que posso ensinar
6. Meus gostos por categoria
7. Dias cheios
0. Sair
> 6
Categoria (serie, comida, hobby, musica...): hobby

== Gosto de (hobby) ==
  - leitura

  === Assistente pessoal de eduarda ===
1. Minhas disciplinas
2. Agenda de um dia
3. Horários livres
4. Estou livre em...?
5. Linguagens que posso ensinar
6. Meus gostos por categoria
7. Dias cheios
8. Minha regra
0. Sair
> 8

== Dias livres para praticar hobbies ==
  - sexta: leitura
  - sabado: leitura
