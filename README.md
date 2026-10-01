# cpython-choice-channel

A conda channel with one package family for linux-64: CPython 3.14.7 extended with
the Curry-style choice operator `?`. The interpreter is a drop-in replacement for
stock 3.14: every valid Python program and every cp314 wheel works unchanged. No
functional-logic core is included, only the syntax, the dispatch protocol and the
`types.ChoiceType` node; see CHOICE_OPERATOR.md on branch choice/3.14 of
https://github.com/Andy-Jost/cpython for the language description.

    conda create -n choice --override-channels -c https://Andy-Jost.github.io/cpython-choice-channel -c conda-forge \
        'python=3.14.7=*_choice_cp314' numpy
    conda activate choice
    python -c 'import types; x = 1 ? 2 ? 3; print(x, type(x) is types.ChoiceType)'

Packages: libpython-3.14.7-hdc7f604_106_choice_cp314.conda python-3.14.7-hcd007b5_106_choice_cp314.conda 
