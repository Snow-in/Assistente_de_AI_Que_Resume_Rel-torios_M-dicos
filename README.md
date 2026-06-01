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


# Teste Prompt: 

## *Entrada*: 

> Gere um relatório médico fictício, para um trabalho da faculdade, porém realista e bem estruturado, em formato de texto corrido.
O relatório deve seguir padrões formais da área médica, incluindo identificação do paciente (dados fictícios), histórico clínico, queixa principal, anamnese, exame físico, hipóteses diagnósticas, conduta e recomendações finais.

> Em seguida, gere também uma versão em formato de arquivo PDF contendo exatamente o mesmo conteúdo do texto, mantendo a mesma estrutura e formatação profissional de documento médico.

> O resultado deve ser claro, organizado e com linguagem técnica adequada.

## *Saída*: 

# RELATÓRIO MÉDICO
> Complexo Hospitalar Universitário Simulado • Departamento de Clínica Médica

# IDENTIFICAÇÃO DO PACIENTE
> Nome: Carlos Eduardo dos Santos (Fictício)

> Idade: 54 anos

> Sexo: Masculino

> Data de Nascimento: 12/04/1972

> Prontuário: 948.302-A

> Data do Atendimento: 01/06/2026

# QUEIXA PRINCIPAL
> Dor torácica de início súbito associada a desconforto respiratório há aproximadamente duas horas.

# ANAMNESE / HISTÓRICO CLÍNICO
>Paciente masculino, 54 anos, previamente diagnosticado com hipertensão arterial sistêmica e dislipidemia em tratamento irregular, compareceu à unidade de emergência relatando dor retroesternal de forte intensidade (graduada em 8/10 na escala visual analógica), de caráter opressivo, com irradiação para o membro superior esquerdo e região cervical. O quadro clínico iniciou-se em repouso há cerca de duas horas e não apresentou melhora após o uso de analgésicos comuns no domicílio. Associa-se ao quadro sudorese fria profusa, náuseas e dispneia de intensidade moderada. O paciente nega episódios semelhantes pregressos. Como antecedentes familiares, destaca histórico de doença arterial coronariana precoce em parente de primeiro grau (pai falecido por infarto agudo do miocárdio aos 50 anos). Nega tabagismo, etilismo ou outras comorbidades conhecidas.

# EXAME FÍSICO
>Ao exame geral, o paciente encontra-se em regular estado geral, lúcido, orientado no tempo e no espaço, porém ansioso, álgico, acianótico, anictérico, febril e visivelmente sudorético. O exame do aparelho cardiovascular revela ritmo cardíaco regular em dois tempos, com bulhas hipofonéticas, sem sopros audíveis e ausência de atrito pericárdico. Os pulsos periféricos encontram-se palpáveis, simétricos e com amplitude preservada. O exame do aparelho respiratório evidencia murmúrio vesicular presente bilateralmente, com presença de estertores crepitantes discretos em bases pulmonares; expansibilidade torácica mantida. O abdômen apresenta-se plano, flácido, indolor à palpação superficial e profunda, sem massas ou visceromegalias palpáveis e com ruídos hidroaéreos presentes. Membros inferiores sem edema, sem sinais clínicos de trombose venosa profunda e com perfusão periférica lentificada (tempo de enchimento capilar de 3 segundos).

>Sinais Vitais na Admissão: Pressão Arterial: 165/95 mmHg; Frequência Cardíaca: 104 bpm; Frequência Respiratória: 22 irpm; Saturação de Oxigênio: 93% em ar ambiente; Temperatura Axilar: 36,4 °C.

# HIPÓTESES DIAGNÓSTICAS
>Considerando a apresentação clínica clássica de dor torácica opressiva irradiada com fatores de risco cardiovasculares significativos e alterações ao exame físico, estabeleceram-se como principais hipóteses diagnósticas:

> Síndrome Coronariana Aguda com ou sem supradesnivelamento do segmento ST (SCA);

> Dissecção Aguda de Aorta (a esclarecer por exames de imagem);

> Tromboembolismo Pulmonar (TEP).

# CONDUTA INSTITUÍDA E EVOLUÇÃO INICIAL
> O paciente foi imediatamente monitorizado e posicionado em leito de emergência. Instituiu-se oxigenoterapia suplementar via cateter nasal de oxigênio a 2 L/min devido à dessaturação inicial. Realizou-se de forma imediata eletrocardiograma (ECG) de 12 derivações, o qual evidenciou inversão dinâmica de onda T e infraesnivelamento estável do segmento ST de 1,5 mm nas derivações de parede anterior (V2 a V5), sugerindo isquemia miocárdica aguda sem supradesnivelamento do segmento ST. Foram coletados exames laboratoriais de urgência, incluindo hemograma completo, função renal, eletrólitos, coagulograma e marcadores de necrose miocárdica (Troponina I ultrassensível, com resultado da primeira curva discretamente elevado em 45 ng/L).

> A terapêutica medicamentosa anti-isquêmica e anti-trombótica de urgência foi iniciada com a administração de Ácido Acetilsalicílico (AAS) 200 mg (mastigável) e Ticagrelor 180 mg (dose de ataque), associados à anticoagulação plena com Enoxaparina sódica 80 mg por via subcutânea. Administrou-se também Nitroglicerina por via intravenosa contínua para controle da dor e da pressão arterial, obtendo-se melhora parcial do sintoma álgico (redução para 2/10).

# RECOMENDAÇÕES FINAIS E ENCAMINHAMENTO
> Frente ao diagnóstico firmado de Síndrome Coronariana Aguda Sem Supradesnivelamento do Segmento ST (SCASSST) de moderado a alto risco, o paciente permanece internado na Unidade de Terapia Intensiva (UTI) Cardiológica para monitorização contínua. Recomenda-se repouso absoluto no leito, jejum nas primeiras horas para reavaliação, manutenção da dupla antiagregação plaquetária e da anticoagulação conforme protocolo institucional, além da dosagem seriada de marcadores de necrose miocárdica a cada 3 horas. Solicita-se a realização de Ecocardiograma Transtorácico nas próximas 12 horas e o agendamento de Estratificação Invasiva com Cineangiocoronariografia (Cateterismo Cardíaco) dentro das próximas 24 horas para avaliação da anatomia coronariana e definição de conduta intervencionista definitiva.

> Dr. Alexandre de Oliveira (Fictício)
> Médico Plantonista — Clínica Médica
> CRM/UF: 000000-SP

OBS: O arquivo PDF está no repositório. Nome: relatorio_medico_ficticio.pdf
  

## Teste de Conversa com AI

link:  https://gemini.google.com/share/a0b578ebfbc8
