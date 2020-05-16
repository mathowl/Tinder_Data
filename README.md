<h1 align="center">
  <b>tinderdata</b>
</h1>

A very simple package to get insight on your Tinder usage.

## Install

This code is compatible with `Python 3.6.1+`.
If for some reason you have a need for it, you can simply install it in your virtual enrivonment with:
```bash
pip install tinderdata
```

## Usage

This utility requires that you export your data from the Tinder platform, as described [here](https://www.help.tinder.com/hc/en-us/articles/115005626726-How-do-I-request-a-copy-of-my-personal-data-).
You should obtain a single `tinderdata.json` file, which is the input required for this script.

Usage goes as follows:
```
usage: __main__.py [-h] -p PATH [--show-figures SHOW] [--save-figures SAVE]
                   [-l LOG_LEVEL]

Getting insight on your Tinder usage.

optional arguments:
  -h, --help            show this help message and exit
  -p PATH, --path-to-data PATH
                        Absolute path to the json file of your tinder data.
                        Can be absolute or relative.
  --show-figures SHOW   Whether or not to show figures when plotting insights.
                        Defaults to False.
  --save-figures SAVE   Whether or not to save figures when plotting insights.
                        Defaults to False.
  -l LOG_LEVEL, --logs LOG_LEVEL
                        The base console logging level. Can be 'debug',
                        'info', 'warning' and 'error'. Defaults to 'info'.
```

An example command is then:
```
python -m tinderdata -p path_to_tinderdata.json --logs debug --save-figures True
```

The script print out a number of insight statements, and finally the text you should paste to get a Sankey diagram.
It will then create a `plots` folder and populate it with visuals.

You can otherwise import the high-level object from the package, and use at your convenience:
```python
from tinderdata import TinderData

tinder = TinderData("tinderdata.json")
tinder.output_sankey_string()
tinder.plot_messages_loyalty(showfig=True, savefig=False)
```

## Output example

Here are examples of the script's outputs:
<p align="center">
  <img src="https://github.com/fsoubelet/Tinder_Data/blob/master/plots/messages_monthly_stats.png"/>
</p>

<p align="center">
  <img src="https://github.com/fsoubelet/Tinder_Data/blob/master/plots/swipes_weekdays_stats.png"/>
</p>

## License

Copyright &copy; 2019-2020 Felix Soubelet. [MIT License][license]

[license]: https://github.com/fsoubelet/Tinder_Data/blob/master/LICENSE