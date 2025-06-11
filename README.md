# Turkish Food VLM Benchmark

> **Note:** Full code and resources will be made publicly available upon the acceptance of the associated research paper.

This repository contains the code and experimental setup for the research paper: **"Performance comparison of multimodal vision-language models in classifying Turkish dishes"**

## Abstract

This study presents the first comprehensive benchmark of seven open-source multimodal vision-language models with Turkish language support on two image datasets of Turkish cuisine, TurkishFoods-15 and TurkishFoods-25. All models were evaluated zero-shot, without additional training or fine-tuning, utilizing fully standardized Turkish system and user prompts.

## Repository Structure

```
├── src/                    # Source code
│   ├── models/            # Model loading and inference
│   ├── data/              # Data loading and preprocessing
│   ├── evaluation/        # Evaluation metrics and analysis
│   └── visualization/     # Plotting and figure generation
├── scripts/               # Execution scripts
├── configs/               # Configuration files
├── requirements.txt       # Python dependencies
├── environment.yml        # Conda environment
└── README.md             # This file
```

## Models Evaluated

1. **Aya Vision 32B** 
2. **Gemma 3 27B** 
3. **InternVL3 38B** 
4. **Qwen2-VL 72B-AWQ** 
5. **Qwen2.5-VL 72B-AWQ**
6. **Cosmos-LLaVA**
7. **Phi-4 Multimodal** 

## Datasets

- **TurkishFoods-15**: 7,411 images across 15 Turkish dish categories
- **TurkishFoods-25**: 11,461 images across 25 Turkish dish categories

## Installation

### Using Conda (Recommended)

```bash
conda env create -f environment.yml
conda activate turkish-food-vlm
```

### Using pip

```bash
pip install -r requirements.txt
```

## Usage

### 1. Single Model Evaluation

```bash
python scripts/evaluate_model.py \
    --model_type aya \
    --model_name CohereForAI/aya-vision-32b \
    --dataset_path turk15 \
    --temperature 1.0 \
    --top_p 1.0
```

### 2. Run All Evaluations

```bash
python scripts/run_all_experiments.py
```

### 3. Generate Analysis and Figures

```bash
python scripts/analyze_results.py
python scripts/generate_figures.py
```

## Configuration

Edit `configs/model_config.py` to modify:
- Model paths and configurations
- Dataset configurations
- Evaluation parameters

## Results

Key findings from our evaluation:

- **Best on TurkishFoods-15**: Aya Vision 32B (85.9% weighted F1-score)
- **Best on TurkishFoods-25**: Gemma 3 27B (76.7% weighted F1-score)
- **Most consistent**: Aya Vision 32B, Gemma 3 27B, Qwen2-VL 72B-AWQ, InternVL3 38B
- **Fastest inference**: Cosmos-LLaVA and Phi-4 Multimodal (but lower accuracy)

## Citation

If you use this code or findings in your research, please cite:

```bibtex
@article{bicakci2025turkish,
  title={Performance comparison of multimodal vision-language models in classifying Turkish dishes},
  author={Bıçakçı, Yunus Serhat},
  journal={Expert Systems with Applications},
  year={2025},
  publisher={Elsevier}
}
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- The open-source community for providing model checkpoints and tools
- Geospatial Data Science Group at the University of Glasgow for support
- Dataset creators for TurkishFoods-15 and TurkishFoods-25

## Contributing

Please feel free to submit issues, feature requests, and pull requests.
