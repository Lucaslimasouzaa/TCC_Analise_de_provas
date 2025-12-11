# Análise de Padrões Textuais em Vestibulares com Modelos de Linguagem e Sistemas Complexos

> **Trabalho de Conclusão de Curso (TCC)** apresentado ao Departamento de Física da Universidade Estadual de Maringá (UEM) como requisito para obtenção do título de Licenciado em Física.

Este repositório contém o código fonte e as análises desenvolvidas para investigar padrões linguísticos e estatísticos em provas de vestibular, utilizando técnicas de **Processamento de Linguagem Natural (PLN)** e **Sistemas Complexos**.

---

## 📄 Resumo

O projeto analisa os textos das provas de vestibulares da **Universidade Estadual de Maringá (UEM)** entre os anos de 2015 e 2023. O objetivo principal foi investigar se existem padrões textuais (como tamanho, sentimento ou frequência de palavras) que diferenciam sistematicamente alternativas corretas de incorretas, além de aplicar modelos de Deep Learning para classificação automática de questões.

A metodologia envolveu a coleta e limpeza de dados de arquivos `.docx`, análises estatísticas baseadas na **Lei de Zipf** e o uso do modelo de linguagem **BERT** (Bidirectional Encoder Representations from Transformers) para *embeddings* e classificação.

## 🛠️ Tecnologias Utilizadas

O projeto foi desenvolvido em **Python**, utilizando as seguintes bibliotecas e ferramentas:

* **Manipulação de Dados:** `pandas`, `numpy` 
* **Processamento de Texto:** `docx2txt` (extração), `re` (Expressões Regulares)
* **Modelos de Linguagem (LLMs):**
    * BERT (BERTimbau) para embeddings e classificação.
    * FinBERT-PT-BR para análise de sentimentos.
    * VADER (via biblioteca LeIA) para análise de sentimentos baseada em léxico.
* **Machine Learning:** `XGBoost` (implícito na análise de acurácia), `scikit-learn`.
* **Visualização e Redução de Dimensionalidade:** `matplotlib`, `UMAP`.
* **Ambiente:** Jupyter Notebook.

## 📊 Principais Resultados

### 1. Lei de Zipf
A análise confirmou que os textos dos vestibulares seguem a Lei de Zipf ($f(r) \sim r^{-\alpha}$), indicando que as provas seguem padrões linguísticos naturais e universais, sem anomalias estatísticas na frequência das palavras[cite: 303, 329].

### 2. Padrões em Alternativas (Verdadeiras vs. Falsas)
Não foram identificados padrões sistemáticos significativos que permitam diferenciar a resposta correta apenas pela estrutura textual:
* **Tamanho:** A diferença média é de apenas ~10 caracteres a menos nas alternativas falsas, insuficiente para distinção clara.
* **Sentimento:** Tanto a análise com VADER quanto com BERT mostraram distribuições de probabilidade sobrepostas, sem viés emocional.
* **Embeddings:** A projeção vetorial (UMAP) não formou clusters distintos entre verdadeiro e falso.

### 3. Classificação Automática com BERT
Embora a distinção entre verdadeiro/falso tenha sido difícil (Acurácia ~57%), o modelo demonstrou alta performance na classificação de conteúdo:
* **Classificação por Matéria:** 77% de acurácia.
* **Classificação por Grande Área:** 91% de acurácia.

## 📂 Estrutura do Projeto

O fluxo de trabalho foi dividido nas seguintes etapas metodológicas:

1.  **Coleta e Organização:** Separação das provas por ano (Verão, Inverno, PAS) e conversão de PDF para DOCX.
2.  **Limpeza (Cleaning):** Remoção de cabeçalhos, rodapés e instruções irrelevantes.
3.  **Análise Estatística:** Verificação de frequências e Lei de Zipf.
4.  **Modelagem:** Aplicação do BERT para extração de características e classificação supervisionada.

## 👨‍🔬 Autor

**Lucas Augusto Lima de Souza** 
* Licenciado em Física pela UEM.
* Orientador: Prof. Dr. Haroldo Valentin Ribeiro.

---

### Citação

> SOUZA, Lucas A. L. **Análise de Padrões Textuais em Vestibulares com Modelos de Linguagem e Métodos de Sistemas Complexos**. 2025. Trabalho de Conclusão de Curso (Licenciatura em Física) - Universidade Estadual de Maringá, Maringá, 2025.
