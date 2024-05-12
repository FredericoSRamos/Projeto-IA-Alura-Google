# Projeto-IA-Alura-Google
Este código Python é um sistema de busca inteligente para vídeos do YouTube. Ele usa IA para entender o conteúdo dos vídeos e encontrar aqueles mais relevantes para a sua busca, indo além de simples palavras-chave.

O código apresentado é uma ferramenta para encontrar vídeos relacionados a uma consulta textual. Ele utiliza bibliotecas como google-generativeai, assemblyai, pytube, pandas e numpy para realizar as seguintes tarefas:

Fase 1: Download, transcrição e interpretação dos vídeos

Download do vídeo:
  O usuário fornece links de vídeos do YouTube;
  A biblioteca pytube baixa o áudio do vídeo.

Transcrição do áudio:
  A biblioteca assemblyai transcreve o áudio para texto em português.

Interpretação do texto:
  O modelo de linguagem mais recente do gemini 1.5 pro da Google AI é usado para gerar uma interpretação do texto transcrito.

Criação de embeddings:
  O modelo embedding-001 da Google AI cria embeddings (representações vetoriais) da transcrição para capturar seu significado semântico.
  
Armazenamento dos dados:
  Os dados (título, link, transcrição, interpretação e embeddings) são armazenados em um DataFrame do pandas.
  
Fase 2: Busca por vídeos relacionados

Entrada da consulta:
  O usuário fornece uma consulta textual.
  
Criação de embedding da consulta:
  O modelo embedding-001 cria um embedding para a consulta textual.
  
Cálculo de similaridade:
  O código calcula o produto escalar entre o embedding da consulta e os embeddings de cada vídeo no DataFrame.
  
Identificação do vídeo mais similar:
  O vídeo com o maior produto escalar (maior similaridade semântica) é selecionado.
  
Exibição do resultado:
  O código exibe o vídeo mais relacionado à consulta.
  
Bibliotecas utilizadas:
  google-generativeai: Fornece acesso aos modelos de linguagem e embedding da Google AI. #!pip install google-generativeai
  assemblyai: Realiza a transcrição de áudio para texto. #!pip install assemblyai
  pytube: Faz download de vídeos do YouTube. #!pip install pytube
  pandas: Cria e manipula DataFrames para armazenar os dados. Já vem no Google Colab (!pip install pandas)
  numpy: Realiza cálculos numéricos, como o produto escalar. Já vem no Google Colab (!pip install numpy)
  
Observações:

É necessário configurar as chaves de API para google-generativeai (https://aistudio.google.com/app/apikey) e assemblyai (https://www.assemblyai.com/app) no código;
O código utiliza modelos específicos da Google AI - Gemini 1.5 pro latest e embedding-001 - outros modelos podem ser utilizados;
A qualidade da busca depende da qualidade das transcrições, interpretações e embeddings;
Em resumo, o código cria um sistema de busca que encontra vídeos relacionados a uma consulta textual, utilizando técnicas de processamento de linguagem natural e aprendizado de máquina.
