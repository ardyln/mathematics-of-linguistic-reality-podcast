# Mathematics of Linguistic Reality: the podcast
This GitHub repo contains podcast episodes of "Mathematics of Linguistic Reality" by Cem Bozşahin. Two AI hosts named Alex and Sam discuss each chapter.

> The episodes were made entirely with local AI on one laptop and nothing went to a cloud AI service.

**[Download the episodes (MP3)](../../releases/latest)**

| | | |
|---|---|---|
| 1 | Basics revisited | 32 min |
| 2 | Mathematics and philosophy of linguistics | 26 min |
| 3 | Degrees of structure from string admissibility | 27 min |
| 4 | Formal grammars: describing admissible strings | 10 min |
| 5 | Automata: computing admissible strings | 27 min |
| 6 | Mathematics of linguistic embedding and delineation | 28 min |

## How they were made
1. book2podcast (https://github.com/ardyln/book2podcast) runs the whole process
2. Docling (https://github.com/docling-project/docling) read the book's PDF on the GPU; book2podcast split it into 6 chapters
3. Open Notebook (https://github.com/lfnovo/open-notebook) had a language model in Ollama (https://ollama.com) write an outline, then a two-host script, per chapter
4. Kokoro text-to-speech (https://github.com/hexgrad/kokoro), served by Speaches (https://github.com/speaches-ai/speaches), voiced the hosts; lines mixed into one MP3 per chapter
5. The language model and the voices took turns on the 6 GB GPU; book2podcast unloads one before the other runs

Made on 30 October 2026; about 13 minutes per episode, a little over an hour for all six.

Caveat: No person wrote or reviewed the scripts; the hosts can simplify, misstate or invent details; a way into the book, not a substitute; check anything important against the book.

## The machine
| Component | Specification |
|---|---|
| Computer | HP Victus 15 gaming laptop (15-fa1xxx) |
| CPU | Intel Core i7-13700H, 14 cores, 20 threads |
| GPU | NVIDIA GeForce RTX 4050 Laptop GPU, 6 GB VRAM, driver 615.71.09 |
| Memory | 14 GiB available to the system |
| Storage | 1 TB NVMe SSD, SK hynix PC801 |
| OS | Ubuntu 26.10, Linux 7.3 |

| Component | Specification |
|---|---|
| Script writing (outline and dialogue) | gemma4-abliterated-e4b-text in Ollama 0.34.0; Gemma 4 E4B variant, 7.5B parameters, Q4_K_M quantisation, 62k-token context |
| Voices | Kokoro-82M v1.0 (ONNX) via Speaches; am_michael = Alex, af_heart = Sam |
| PDF reading | Docling 2.144.0 |
| Orchestration | Open Notebook v1, book2podcast |

The language model and the voices took turns on the 6 GB GPU; book2podcast unloads one before the other runs.

## Free and open-source tools

Every tool and model used is free and open source (the models are open-weight), apart from NVIDIA's GPU driver libraries noted below.

| Tool or model | Used for | License |
|---|---|---|
| [book2podcast](https://github.com/ardyln/book2podcast) | running the whole process | GPL-3.0 |
| [Docling](https://github.com/docling-project/docling) | reading the PDF | MIT |
| [RapidOCR](https://github.com/RapidAI/RapidOCR) | OCR inside Docling | Apache-2.0 |
| [PyTorch](https://github.com/pytorch/pytorch) | running Docling's models on the GPU | BSD-3-Clause |
| [Open Notebook](https://github.com/lfnovo/open-notebook) | outline, script and audio pipeline | MIT |
| [Ollama](https://github.com/ollama/ollama) | running the language models | MIT |
| [Gemma 4](https://huggingface.co/google/gemma-4-E4B-it) (E4B and 12B, community "abliterated" variants) | writing the scripts and this README | Apache-2.0 (open weights) |
| [Speaches](https://github.com/speaches-ai/speaches) | serving the voices | MIT |
| [Kokoro-82M](https://huggingface.co/hexgrad/Kokoro-82M) | the voices | Apache-2.0 (open weights) |
| [pi](https://github.com/earendil-works/pi-mono) | running the model that wrote this README | MIT |
| Ubuntu 26.10, Linux 7.3 | operating system | mostly GPL-2.0 and other free licenses |

The one exception is the NVIDIA driver. Its kernel module is open source (MIT/GPL-2.0), but the user-space libraries that CUDA runs on are under NVIDIA's proprietary license. They are free to use, but not open source.

"Open weights" means the trained model files are published under the license; the data they were trained on is not.

## About this README
This README was also written by a local language model, gemma4-abliterated-12b-64k (Gemma 4 12B variant) run through the pi agent on the same laptop, from a list of facts, with the title, intro and download link fixed by hand and the section on free and open-source tools added by hand.

## Attribution and license
The episodes are based on "Mathematics of Linguistic Reality" by Cem Bozşahin, © 2026, CC BY 4.0 (https://creativecommons.org/licenses/by/4.0/). Each chapter was turned into an AI-generated spoken conversation that summarises, paraphrases and discusses it; not the book's text. Neither the author nor the publisher made or endorses the episodes. Anyone may share and adapt the episodes, also commercially, if they credit the book (title, author, license) and this adaptation, and say whether they changed them.
