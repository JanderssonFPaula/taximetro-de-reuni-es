# 🚕 Taxímetro de Reunião

Um taxímetro para reuniões: mostra em tempo real quanto a reunião está custando. Se a reunião estourar o tempo previsto, entra a **Tarifa 2** e o custo por minuto aumenta — igual taxímetro de verdade.

Feito em um único arquivo HTML, sem dependências e sem instalação. Roda 100% offline em qualquer navegador.

## 🎯 Por que usar

Reunião tem custo, mas ninguém vê. Com o taxímetro rodando na tela (ou compartilhado no projetor), todo mundo enxerga o dinheiro pingando — e a reunião tende a acabar no horário.

## 🚀 Como usar

1. Baixe o arquivo `taximetro-reuniao.html`
2. Dê dois cliques para abrir no navegador (Chrome, Edge, Firefox...)
3. Configure a tarifa
4. Clique em **▶ Iniciar corrida**

Não precisa de internet, servidor nem instalação. Dica: compartilhe a aba do navegador na chamada do Teams/Meet para todo mundo ver o custo subindo. 😄

## ⚙️ Configuração

| Campo | O que significa | Exemplo |
|---|---|---|
| **Valor (R$)** | Quanto custa o bloco de tempo | `100` |
| **...a cada (minutos)** | Tamanho do bloco de tempo | `60` → R$ 100 por hora (R$ 1,67/min) |
| **Duração prevista (min)** | Tempo planejado da reunião | `30` |
| **Multiplicador se estourar** | Fator aplicado ao custo/min após passar do previsto | `2` → custo por minuto dobra |

> 💡 **Como estimar o valor:** some o custo/hora dos participantes. Ex.: 5 pessoas a R$ 40/h = **R$ 200 a cada 60 minutos**.

## 🧮 Como o custo é calculado

- **Tarifa 1** (dentro do tempo previsto):
  `custo = minutos × (valor ÷ tempo)`
- **Tarifa 2** (após estourar o previsto):
  `custo = previsto × tarifa1 + minutos excedentes × tarifa1 × multiplicador`

O cálculo usa timestamp real (`Date.now()`), então o valor continua correto mesmo se a aba ficar em segundo plano.

## 🖥️ Funcionalidades

- ⏱️ Custo acumulado atualizado em tempo real
- 🚩 Bandeira **TARIFA 1 / TARIFA 2** — o visor fica vermelho e pisca quando a reunião estoura
- ⏳ Tempo decorrido, tempo restante (ou excedente) e custo por minuto atual
- ⏸️ Pausar / retomar / zerar a corrida
- 🔒 Configuração travada enquanto o taxímetro está rodando (edite pausado)
- 📑 O valor acumulado aparece no título da aba do navegador
- 📱 Interface responsiva (funciona no celular também)

## 🛠️ Tecnologias

- HTML + CSS + JavaScript puro (vanilla), tudo em um arquivo
- Fontes: Archivo e Chivo Mono (Google Fonts — se estiver offline, usa fonte do sistema)
- Sem frameworks, sem build, sem dependências

## 📁 Estrutura

```
taximetro-reuniao.html   ← o app inteiro (abrir no navegador)
README.md                ← este arquivo
```

## 📝 Licença

Uso livre. Modifique à vontade.
