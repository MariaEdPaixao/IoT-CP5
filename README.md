# IoT-CP5: Redes Neurais e Visão Computacional

## Objetivo
Demonstrar duas abordagens de Visão Computacional para detecção de placas de motos brasileiras e OCR para extrair os dados desta placa, além de um exemplo de redes neurais em Keras.

## Estrutura
- CP5_AzureVC_2parte.ipynb (Hugging Face + Azure OCR)
- FINAL_Exemplo_Redes_Neurais_Com_Keras.ipynb (referência Parte 01)
- notebooks/
  - roboflow_workflow_runner.py (execução de workflow do Roboflow via API)
- workflows/
  - roboflow_workflow.json (workflow sanitizado — usa variável de ambiente GEMINI_API_KEY)
- results/
  - Evidências geradas (imagens e métricas)
- print_moto_placa.png (imagem de teste)

## Ferramentas (2 escolhidas)
- Microsoft Azure Computer Vision – OCR (Image Analysis READ)
- Hugging Face – modelo YOLOS para detecção de placas

Opcional/documentado: Roboflow (workflow de inferência e OCR de placa)

## Dataset/Imagens
- Imagem de teste local: print_moto_placa.png

## Hiperparâmetros e configs principais
- Modelo: nickmuchi/yolos-small-finetuned-license-plate-detection
- Threshold de detecção: 0.5
- Pré-processamento: conversão para RGB, crop dinâmico da placa
- OCR: Azure AI Vision Image Analysis (READ)

## Como executar (Colab ou local)
1. Defina variáveis de ambiente (ou .env) para o Azure e Roboflow:
   - VISION_ENDPOINT
   - VISION_KEY
   - ROBOFLOW_API_KEY (opcional para workflow)
   - GEMINI_API_KEY (se usar OCR do workflow Roboflow)
2. Execute o notebook `CP5_AzureVC_2parte.ipynb`.
3. Resultados serão salvos em `results/`.
4. (Opcional) Execute o script do Roboflow em `notebooks/roboflow_workflow_runner.py` para gerar `results/roboflow_output.json` e imagens.

## Comparativo resumido
- Hugging Face + Azure:
  - Vantagens: flexibilidade, fácil trocar modelos, OCR robusto.
  - Desvantagens: integrações múltiplas, custo do serviço OCR.
- Roboflow Workflow:
  - Vantagens: pipeline pronto de visão + OCR, fácil compartilhar.
  - Desvantagens: dependência de serviço externo e chaves; latência variável.

Métricas coletadas (salvas em `results/metrics_hf_azure.json`): latência da detecção, nº de caixas e confiança média, latência do OCR.

## Resultados e observações
- Imagens geradas: `results/original_with_bbox.png`, `results/cropped_plate.png`
- Texto OCR: `results/ocr_plate.txt`
- Métricas: `results/metrics_hf_azure.json`

