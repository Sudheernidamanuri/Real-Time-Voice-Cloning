# Real-Time Voice Cloning

## Overview
This project implements real-time voice cloning using deep learning techniques. It enables users to clone voices from audio samples and generate new speech in the cloned voice.

## Features
- Real-time voice cloning capabilities
- Deep learning-based voice synthesis
- Sample audio data included
- Comprehensive documentation

## Project Structure
```
Real-Time-Voice-Cloning/
├── code/           # Source code files
├── samples/        # Sample audio data
└── documentation/  # Project documentation (PDF)
```

## Requirements
- Python 3.x
- TensorFlow/PyTorch
- NumPy
- Other dependencies (see requirements.txt)

## Installation
1. Clone this repository
```bash
git clone https://github.com/Sudheernidamanuri/Real-Time-Voice-Cloning.git
cd Real-Time-Voice-Cloning/Real-Time-Voice-Cloning-master
```

2. Install required dependencies
```bash
pip install -r requirements.txt
```

3. Download pre-trained models (if applicable)

## Quick Start Examples

### Running the Demo

#### Toolbox Demo (GUI)
Launch the interactive toolbox with a graphical interface:
```bash
python demo_toolbox.py
```

With optional arguments:
```bash
python demo_toolbox.py -d <datasets_root> --cpu
```

#### Command Line Demo
Run the CLI demo for voice cloning:
```bash
python demo_cli.py
```

With custom encoder/synthesizer/vocoder models:
```bash
python demo_cli.py --enc_model_fpath path/to/encoder.pt --syn_model_fpath path/to/synthesizer.pt --voc_model_fpath path/to/vocoder.pt
```

### Data Preprocessing

#### Encoder Preprocessing
Preprocess datasets for encoder training:
```bash
python encoder_preprocess.py <datasets_root> -d <dataset_name>
```

Example with LibriSpeech:
```bash
python encoder_preprocess.py /path/to/datasets -d librispeech_other
```

#### Synthesizer Preprocessing
Preprocess audio for synthesizer:
```bash
python synthesizer_preprocess_audio.py <datasets_root> -o <out_dir> -d <dataset_name>
```

Preprocess embeddings:
```bash
python synthesizer_preprocess_embeds.py <synthesizer_root> -e <encoder_model_fpath>
```

#### Vocoder Preprocessing
Preprocess data for vocoder training:
```bash
python vocoder_preprocess.py <datasets_root> -m <model_name> -d <dataset_name>
```

### Training Models

#### Train the Encoder
```bash
python encoder_train.py <run_id> <clean_data_root> -m <models_dir>
```

Example:
```bash
python encoder_train.py my_run /path/to/preprocessed_data -m saved_models/
```

#### Train the Synthesizer
```bash
python synthesizer_train.py <run_id> <syn_dir>
```

Example with custom parameters:
```bash
python synthesizer_train.py my_synth_run /path/to/synth_data --backup_every 5000 --save_every 1000
```

#### Train the Vocoder
```bash
python vocoder_train.py <run_id> <syn_dir> -m <model_name>
```

Example:
```bash
python vocoder_train.py my_vocoder_run /path/to/synth_data -m wavernn
```

### Common Options

Most training scripts support:
- `--backup_every <n>`: Backup model every n steps
- `--save_every <n>`: Save model every n steps  
- `--force_restart`: Restart training from scratch
- `--cpu`: Run on CPU instead of GPU

## Usage
Detailed usage instructions can be found in the documentation folder.

## Documentation
Complete project documentation including methodology, architecture, and results is available in the PDF files within the repository.

## B.Tech Project
This is a B.Tech project focused on implementing real-time voice cloning using state-of-the-art deep learning techniques.

## License
This project is for educational purposes.

## Contact
For questions or issues, please open an issue in this repository.
