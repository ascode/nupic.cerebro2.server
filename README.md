# Cerebro 2 Server

Makes a CLA model's state history available to the [Cerebro 2 client](https://github.com/numenta/nupic.cerebro2).

## Installation

Requirements:

- [NuPIC](https://github.com/numenta/nupic)

Install other requirements:

    pip install -r requirements.txt

Install the Cerebro 2 Python library:

    cd py
    python setup.py install

## Usage

First, patch your model:

    // Assuming `model` is a CLA model you already have
    from cerebro2.patcher import Patcher
    Patcher().patchCLAModel(model)

You can also patch an SP or a TP directly:

    // Assuming `sp` and `tp` are already defined
    from cerebro2.patcher import Patcher
    Patcher().patchSP(sp)
    Patcher().patchTP(tp)

Then, after the model / SP / TP has through a number of iterations:

    python server.py

Finally, switch to [nupic.cerebro2](https://github.com/numenta/nupic.cerebro2) to visualize your model / SP / TP.

## Demos

See `/demo`.

## Notes

- By default, the model state history is saved to `/tmp/cerebro2`.
