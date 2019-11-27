# viwikipi

Vietnamese Wikipedia Paraphase Identity experiments on Transformers

## Prerequisites

[Git LFS](https://git-lfs.github.com/) is required to clone this repository.
After installation (the plugin is available on most GNU/Linux distributions),
set it up using

    git lfs install

Next, clone this repo and install the dependencies:

    git clone https://github.com/McSinyx/viwikipi.git
    cd viwikipi/
    pip3 install -r requirements.txt

## Usage

At the moment, GLUE for Bert can be fine-tuned using

```sh
tools/glue --model-type=bert --model=bert-base-multilingual-cased \
           --output-dir=bert --log-file=bert/$(date -Is).log
```

Filtering for highly lossed example may assist training, which can be done by

```sh
tools/filter -t bert -m bert mrpc/train.tsv train.tsv
```

Paraphase identity labeling can be achieved via

```sh
tools/label -t bert -m bert tests/test.json tests/submission.csv
```

XLM models can be used similarly by replacing `bert*` with `xlm*`.

## Copying

Training data (`mrpc`, `tests`) are provided by
[Zalo AI Challenge 2019](https://challenge.zalo.ai/). These are derivatives
of texts from Wikipedia, which are licensed under
[CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/).

Vietnamese WordNet (`wn`) is taken from
[zeloru/vietnamese-wordnet](https://github.com/zeloru/vietnamese-wordnet),
which is a derivative of Wiktionary, which is also licensed under CC BY-SA 3.0.

For consistency, the two resources above and their modifications are released
under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/).

`tools/glue` is basically [ripped-off from transformers](https://github.com/huggingface/transformers/blob/master/examples/run_glue.py)
with saner defaults and GNU-style long arguments.  The original version
is licenced under [Apache-2.0](http://www.apache.org/licenses/LICENSE-2.0).

The entire codebase, including this script, is then released under
[GNU AGPLv3](https://www.gnu.org/licenses/agpl-3.0.en.html).
