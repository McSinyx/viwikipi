# Vietnamese Wikipedia Paraphase Identity experiments

At the moment, GLUE for Bert can be executed using

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

## Attributions

`glue` is basically [ripped-off from transformers](https://github.com/huggingface/transformers/blob/master/examples/run_glue.py)
with saner defaults and GNU-style long arguments.

Training data are provided by
[Zalo AI Challenge 2019](https://challenge.zalo.ai/). These are derivatives
of texts from Wikipedia, which are licensed under
[CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/).

Vietnamese WordNet is taken from
[zeloru/vietnamese-wordnet](https://github.com/zeloru/vietnamese-wordnet),
which is a derivative of Wiktionary, which is also licensed under CC BY-SA 3.0.

## Contributing

This project is to be released under GNU AGPLv3 which requires each source file
to have a header stating so.  Please navigate to existing ones for examples.

The current codebase is linted using [flake8](https://gitlab.com/pycqa/flake8).
Feel free to blacklist any error/warning you feel unnecessary in `tox.ini`.
