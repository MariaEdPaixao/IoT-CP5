# 🚀 IoT-CP5: Redes Neurais e Visão Computacional

## 🎯 Objetivo do Projeto
Este projeto demonstra duas abordagens complementares de **Visão Computacional** aplicadas à **detecção e leitura de placas de motocicletas brasileiras**, além de um **exemplo de rede neural desenvolvida em Keras** (Parte 1 da CP5).

As soluções exploram:
1. 🧠 **Redes Neurais com Keras**  
2. 👁️ **Detecção e OCR com Hugging Face + Azure Vision**  
3. 🧩 **Workflow Roboflow** (fornecido em JSON para replicação)

---

## 🧠 Parte 01 – Redes Neurais (Keras)
`colocar primeira parte aqui` 

---

## 👁️ Parte 02 – Visão Computacional
Comparação entre duas ferramentas distintas aplicadas ao mesmo objetivo: **detectar e ler placas de veículos**.

### 🧰 Ferramentas Utilizadas
| Ferramenta | Uso Principal | Descrição |
|-------------|----------------|------------|
| 🤗 **Hugging Face (YOLOS)** | Detecção de placas | Modelo pré-treinado `nickmuchi/yolos-small-finetuned-license-plate-detection` |
| ☁️ **Microsoft Azure Computer Vision** | OCR (Image Analysis - READ API) | Extração de texto da placa detectada |
| 🧩 **Roboflow** | Workflow de visão e OCR | JSON disponível para replicação na plataforma Roboflow |

---

## 📁 Estrutura do Repositório
```
IoT-CP5/
├── notebooks/
│ └── CP5_AzureVC_2parte.ipynb # Detecção e OCR (Hugging Face + Azure)
├── workflows/
│ └── roboflow_workflow.json # Workflow exportável (para uso na plataforma Roboflow)
├── results/
│ ├── original_with_bbox.png
│ ├── cropped_plate.png
│ ├── ocr_plate.txt
│ └── metrics_hf_azure.json
├── images/
│ └── print_moto_placa.png # Imagem de teste
├── FINAL_Exemplo_Redes_Neurais_Com_Keras.ipynb
└── README.md
```
---

## 🧩 Dataset / Imagens
- 📸 Imagem de teste: `images/print_moto_placa.png`  
- 📚 Dataset público (Roboflow):  
  👉 [Roboflow Universe Dataset's](https://universe.roboflow.com/zeroexperiments/motorcycle-license-plate-skrdr)

---

## ⚙️ Hiperparâmetros e Configurações Principais (Visão Computacional)
| Parâmetro | Valor | Descrição |
|------------|--------|-----------|
| Modelo | `nickmuchi/yolos-small-finetuned-license-plate-detection` | Detecção de placas |
| Threshold de confiança | `0.5` | Filtro mínimo de detecção |
| Pré-processamento | Conversão RGB + crop dinâmico | Otimiza a entrada do OCR |
| OCR | Azure AI Vision Image Analysis (READ) | Extração de caracteres da placa |

---

## ▶️ Como Executar

### 🔧 Configuração de Ambiente
Defina suas variáveis de ambiente no sistema ou `.env`:
```bash
VISION_ENDPOINT=<seu_endpoint_azure>
VISION_KEY=<sua_chave_azure>
GEMINI_API_KEY=<sua_chave_gemini>
```
### 💻 Execução

1. Execute o notebook principal:
 ```bash
  notebooks/CP5_AzureVC_2parte.ipynb
```
2. Os resultados e métricas serão gerados na pasta `results/`.

---

🌐 Testar o Workflow do Roboflow

Para testar a abordagem alternativa:

1. Acesse Roboflow

2. Crie um novo Workflow.

3. Copie o conteúdo do arquivo: `workflows/roboflow_workflow.json`
  e cole na interface da plataforma.

⚖️ Comparativo entre as Abordagens
| Critério              | 🤗 Hugging Face + Azure                 | 🧩 Roboflow                            |
| --------------------- | --------------------------------------- | -------------------------------------- |
| **Configuração**      | Executado localmente via notebook       | Interface visual, executado em nuvem   |
| **Flexibilidade**     | Alta – livre escolha de modelo e OCR    | Média – depende do pipeline criado     |
| **OCR**               | Azure Vision (alta precisão)            | OCR integrado (precisão variável)      |
| **Latência média**    | ~2 segundos / imagem                    | ~4–5 segundos / imagem                 |
| **Custo**             | OCR pago por requisição                 | Gratuito até certo limite              |
| **Reprodutibilidade** | Notebook Python (totalmente replicável) | Workflow JSON (copiável na plataforma) |

---

## 📊 Resultados e Observações

📂 Resultados salvos em results/:

original_with_bbox.png → imagem com bounding box

cropped_plate.png → recorte da placa

ocr_plate.txt → texto lido via OCR

metrics_hf_azure.json → métricas de latência e confiança

## 🧩 Conclusões

O modelo YOLOS apresentou alta precisão em placas no padrão Mercosul.

O OCR do Azure demonstrou robustez mesmo sob variação de iluminação.

O Roboflow se mostrou útil para validação rápida e replicação do pipeline.

---

## 🎥 Vídeo de Demonstração

👉 Assista à demonstração no YouTube (modo não listado)

---

### 🏆 Integrantes

| Nome | RM | GitHub |
|------|----|---------|
| **Laura de Oliveira Cintra** | RM 558843 | [@lauracintra](https://github.com/Laura-Cintra) 
| **Maria Eduarda Alves da Paixão** | RM 558832 | [@mariaeduarda](https://github.com/MariaEdPaixao) 
| **Vinícius Saes de Souza** | RM 554456 | [@viniciussaes](https://github.com/ViniciuSaeSouza) 

✨ Projeto desenvolvido como parte da disciplina Disruptive Architectures: IoT, IoB & Generative AI – FIAP 2025.

