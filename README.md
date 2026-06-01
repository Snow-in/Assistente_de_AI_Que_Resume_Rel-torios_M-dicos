# 🩺 Assistente IA: Classificador e Tradutor de Relatórios Médicos

Este repositório contém as instruções e a sequência de prompts para configurar uma Assistente de Inteligência Artificial especializada em receber, validar e traduzir relatórios médicos complexos para uma linguagem acessível e leiga.

A IA atua de forma extremamente rigorosa, aceitando **apenas** documentos ou textos relacionados à saúde e rejeitando qualquer desvio de escopo ou tentativa de *prompt injection*.

---

## 🚀 Como Utilizar este Prompt

Como este é um sistema baseado em **prompts sequenciais (encadeados)**, você deve enviar os blocos de texto um por um para a IA, aguardando a confirmação de leitura de cada passo antes de enviar o próximo.

### Passo a Passo da Configuração:

1. **Envie o Prompt 1:** Copie e cole o texto do "Prompt 1". A IA entenderá a lógica de classificação e os exemplos de validação (Few-Shot Prompting).
2. **Envie o Prompt 2:** Copie e cole o texto do "Prompt 2". A IA aprenderá a metodologia de análise baseada em *Chain of Thought* (Pensamento Passo a Passo).
3. **Envie o Prompt 3:** Copie e cole o texto do "Prompt 3". A IA adotará a persona de um médico especialista e didático.
4. **Envie o Prompt 4:** Copie e cole o texto do "Prompt 4 (extra)". Este passo define as restrições finais de segurança e formatos de arquivo aceitos (PDF/TXT).

---

## 🕹️ Comandos de Execução

Após enviar todos os quatro prompts de configuração, utilize os comandos abaixo para interagir com a Assistente:

* `Iniciar` — Ativa a assistente. A partir deste momento, a IA entra em modo de espera aguardando o seu relatório médico.
* `Sair` — Finaliza o modo assistente e encerra a execução da IA.

---

## ⚙️ Arquitetura dos Prompts

### 📋 Teste Prompt (Geração de Dados)
Antes de iniciar a assistente, você pode usar este prompt isolado para gerar um caso de teste realista:
* **Função:** Cria um relatório médico fictício e estruturado (anamnese, hipóteses, conduta) em formato de texto e simula a necessidade de um PDF.

### 🔍 Prompt 1: Classificação e Triagem (Input)
* **Função:** Avalia o texto inserido pelo usuário e o categoriza rigidamente em `[RELATÓRIO_MÉDICO]` ou `[ENTRADA_INVÁLIDA]`.
* **Armazenamento:** Salva os dados validados na variável interna `{{dados_armazenados}}`.

### 🧠 Prompt 2: Pensamento Passo a Passo (Análise)
* **Função:** Aplica engenharia de busca de jargões se a categoria for válida.
* **Mapeamento:** Transforma siglas e termos técnicos complexos em explicações clínicas simples.

### 👨‍⚕️ Prompt 3: Persona e Estruturação (Output)
* **Persona:** Médico especialista, experiente e altamente didático.
* **Formato:** Entrega o resultado em tópicos curtos e visualmente organizados, guiando o paciente através do relatório.

### 🛡️ Prompt 4: Moderação e Segurança Máxima (Restrições)
* **Função:** Aplica um filtro de segurança para blindar a IA.
* **Regra de Ouro:** Rejeita qualquer pergunta fora do escopo médico e limita a aceitação de arquivos estritamente para formatos `.pdf` ou `.txt`.

---

## 📝 Exemplos de Comportamento Esperado

