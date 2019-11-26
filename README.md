# Vietnamese Wikipedia Paraphase Identity experiments

At the moment, GLUE for Bert can be executed using

```sh
tools/glue --model-type=bert --model=bert-base-multilingual-cased \
           --output-dir=bert --log-file=bert/$(date -Is).log
```

Paraphase identity labeling can be achieved via

```sh
tools/label -t bert -m bert tests/test.json tests/submission.csv
```

## Acknowledgements

`glue` is basically [ripped-off from transformers](https://github.com/huggingface/transformers/blob/master/examples/run_glue.py)
with saner defaults and GNU-style long arguments.

Training data are provided by [Zalo AI Challenge 2019](https://challenge.zalo.ai/).

Vietnamese WordNet is taken from
[zeloru/vietnamese-wordnet](https://github.com/zeloru/vietnamese-wordnet).

## Contributing

This project is to be released under GNU AGPLv3 which requires each source file
to have a header stating so.  Please navigate to existing ones for examples.

The current codebase is linted using [flake8](https://gitlab.com/pycqa/flake8).
Feel free to blacklist any error/warning you feel unnecessary in `tox.ini`.
