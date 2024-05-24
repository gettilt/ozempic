<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  cog.outl(f"# {config['name'].title()}")
]]]-->
# Ozempic
<!--//[[[end]]]-->

## Mission

Tilt's mission is to map every theme to a basket of stocks for anyone to invest in. Mappings are AI generated and expert curated.
Expert improvements are accepted if they provide a better representation of a given theme.

## Theme Prompt
<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  cog.outl(config['prompt'])
]]]-->
Ozempic is the next miracle drug and will be used by millions of consumers changing the way the eat and live. An entire population will become healthier
<!--[[[end]]]-->

## Theme Stocks

<!--[[[cog
import cog
import csv
import json

with open('context.json') as file:
  contexts = json.load(file)

def _get_context_str_for_ticker(ticker):
  try:
    context = contexts[ticker]
    context_str = context['chat_gpt'] or context['claude'] or ""
  except KeyError:
    context_str = ""

  return context_str

cog.outl("| Ticker  | Context | Source |")
cog.outl("| ------- | ---- | ---- |")

with open('theme.csv') as file:
  reader = csv.reader(file)
  next(reader) # skip the header
  for row in reader:
    context_str = _get_context_str_for_ticker(row[0])
    cog.outl(f"| {row[0]} | {context_str} | {row[1]} |")
]]]-->
| Ticker  | Context | Source |
| ------- | ---- | ---- |
| ABT | Abbott Laboratories, with its FreeStyle Libre glucose monitoring system, indirectly benefits from increased health awareness. | chat_gpt,claude |
| AMGN | Amgen Inc., with its focus on human therapeutics, could benefit indirectly from the overall growth in the healthcare sector. | chat_gpt,claude,google |
| BMY | Bristol-Myers Squibb Company, with a strong presence in the healthcare market, could see indirect benefits from increased health awareness and drug innovation. | chat_gpt,claude |
| DXCM | DexCom, Inc., a leader in continuous glucose monitoring systems, indirectly benefits as more people manage their health proactively. | chat_gpt |
| GILD | Gilead Sciences, Inc., known for its research in therapeutics, could indirectly benefit from the heightened focus on innovative healthcare solutions. | chat_gpt |
| JNJ | Johnson & Johnson, a diversified healthcare giant, could see indirect benefits through its pharmaceutical and consumer health divisions. | chat_gpt,claude |
| LLY | Eli Lilly and Company, a competitor in the diabetes and weight management market, could innovate or adjust strategies in response to Ozempic's success. | chat_gpt,claude,twitter,google |
| MNKD | MannKind Corporation, involved in inhaled therapeutic products for diabetes, could see indirect benefits as the market for diabetes and weight management drugs expands. | chat_gpt |
| MRK | Merck & Co., Inc., while not directly linked to Ozempic, has a strong portfolio in diabetes care and could benefit from overall market growth. | chat_gpt,claude,twitter,google |
| NVO | Novo Nordisk, the maker of Ozempic, directly benefits from the drug's success. | chat_gpt,claude,google |
| PFE | Pfizer Inc., with its broad healthcare portfolio, could indirectly benefit from the increased focus on health and wellness. | chat_gpt,claude,google |
| PODD | Insulet Corporation, another insulin pump manufacturer, stands to benefit from the broader focus on diabetes and weight management. | chat_gpt |
| REGN | Regeneron Pharmaceuticals, Inc., known for its innovative treatments, could indirectly benefit from increased investment and interest in healthcare solutions. | chat_gpt,claude |
| TNDM | Tandem Diabetes Care, Inc., maker of insulin pumps, could see increased demand alongside the rise in proactive health management. | chat_gpt |
| ABBV |  | claude |
| DHR |  | claude |
| ISRG |  | claude |
| MDT |  | claude |
| UNH |  | claude,twitter |
| VRTX |  | claude |
| META |  | twitter |
| MSFT |  | twitter |
| SMCI |  | twitter |
| UBER |  | twitter |
| VRT |  | twitter |
| AZN |  | google |
| VKTX |  | google |
<!--[[[end]]]-->

## License

<p>
This project is licensed under <a href="./LICENSE">AGPLv3</a>.
</p>


## Contributors

Thank you for your improvements! We appreciate all the contributions from the community.

<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  repo = config['github_repo'].lower()
  cog.outl(f'<a href="https://github.com/gettilt/{repo}/graphs/contributors">')
  cog.outl(f'  <img src="https://contrib.rocks/image?repo=gettilt/{repo}" />')
  cog.outl('</a>')
]]]-->
<a href="https://github.com/gettilt/ozempic/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=gettilt/ozempic" />
</a>
<!--[[[end]]]-->

## Join Our Community

<a href="https://discord.gg/4vYMhRpaMY" target="_blank">
<img src="https://discord.com/api/guilds/1179775688421683220/widget.png?style=banner3" alt="">
</a>
