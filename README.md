# Vietnamese Wikipedia Paraphase Identity experiments

At the moment, GLUE for Bert can be executed using

```sh
./glue --output-dir=bert --model-type=bert --model=bert-base-multilingual-cased
```

`glue` is basically [ripped-off from transformers](https://github.com/huggingface/transformers/blob/master/examples/run_glue.py)
with saner defaults and GNU-style long arguments.

This project is to be released under GNU AGPLv3 which requires each source file
to have a header stating so.  Please navigate to existing ones for examples.

The current codebase is linted using [flake8](https://gitlab.com/pycqa/flake8).
Feel free to blacklist any error/warning you feel unnecessary in `tox.ini`.
