# GPT Image 2.6 na prêÂ¡tica

<div align="center">
  <img src="capa/logo.svg" alt="Arckhé AI" height="48" />
  <p><strong>Arckhé AI</strong></p>
</div>


[![GPT Image 2.6 na prêÂ¡tica](guia/assets/banner.jpg)](https://linnoff88-dev.github.io/

**ê°Å¸â¡Â§ê°Å¸â¡Â· [PortuguêÂªs](README.md) êÂ· ê°Å¸â¡Âºê°Å¸â¡Â¸ [English](README.en.md) êÂ· ê°Å¸â¡Âªê°Å¸â¡Â¸ [EspaêÂ±ol](README.es.md)**

## O que êÂ©

O GPT Image 2.6 êÂ© o modelo de imagem mais novo da OpenAI, que jêÂ¡ roda dentro do ChatGPT e do Codex e tambêÂ©m pode ser usado pela API. Este repositêÂ³rio êÂ© um guia para quem cria imagens para posts, anêÂºncios, logos, histêÂ³rias ou vêÂ­deos e quer tirar proveito das novidades: o ajuste de complexidade (quanto o modelo planeja antes de desenhar), GIF animado, logo em vetor (SVG) e ediêÂ§êÂ£o sêÂ³ na êÂ¡rea que vocêÂª marca. Para usar basta uma conta do ChatGPT; para a API, uma chave da OpenAI (cobrada êÂ  parte da assinatura) e o script `gerar.py`, que sêÂ³ precisa do Python.

## ê°Å¸ââ Guia de uso

Guia completo (landing + passo a passo): **https://linnoff88-dev.github.io/

ê°Å¸Å½Â¬ VêÂ­deo: https://www.youtube.com/watch?v=bHTe58nwW3s

## ConteêÂºdo

| Arquivo | O que êÂ© |
|---|---|
| `guia/` | PêÂ¡gina do guia em PT, com `en/` e `es/` |
| `prompts.md` | 10 prompts prontos: estrutura, complexidade, instruêÂ§êÂµes em sequêÂªncia, cartaz, personagem, referêÂªncia salva, GIF, SVG, markup e ediêÂ§êÂ£o |
| `gerar.py` | Atalho para a API (sêÂ³ biblioteca padrêÂ£o do Python): gera imagem, SVG ou GIF, ou edita com markup, jêÂ¡ com `complexity` e `quality`; confere os limites antes de gastar |
| `exemplos/baixar.py` | Baixa a foto e o cêÂ­rculo de exemplo da OpenAI para testar a ediêÂ§êÂ£o com markup |
| `tests/` | Testes do `gerar.py` sem chamar a API: `python3 -m unittest discover tests` |

## O processo, do inêÂ­cio ao fim

| # | Passo | Comando | Quem faz |
|---|---|---|---|
| 1 | Escolher o modelo: Flare (rêÂ¡pido) ou Sunburst (detalhe) | ê¢â¬â | ê°Å¸Â§Â  vocêÂª |
| 2 | Escrever o pedido em seêÂ§êÂµes (cena, sujeito, detalhes, restriêÂ§êÂµes, texto entre aspas) | `prompts.md` | ê°Å¸Â§Â  vocêÂª |
| 3 | Ver o pedido sem gastar | `python3 gerar.py "<prompt>" --seco` | ê¢Å¡â¢ê¯Â¸Â script |
| 4 | Gerar e comparar: primeiro a complexidade, depois a qualidade | `python3 gerar.py "<prompt>" --complexity high --quality medium` | ê¢Å¡â¢ê¯Â¸Â script (API, cobrado na sua conta) |
| 5 | Conferir mêÂ£o, proporêÂ§êÂ£o, reflexo, contagem e texto | ê¢â¬â | ê°Å¸Â§Â  vocêÂª |
| 6 | Editar uma coisa por vez (ou circular com markup) | `python3 gerar.py "<mudanêÂ§a>" --editar exemplos/cozinha.webp --markup exemplos/circulo.png --complexity low` | ê¢Å¡â¢ê¯Â¸Â script |

No ChatGPT os passos 3, 4 e 6 sêÂ£o sêÂ³ conversa: peêÂ§a a imagem, o GIF ("sprite sheet 3x3 ê¢â¬Â¦ em loop") ou o SVG.

## Uso rêÂ¡pido da API

```bash
export OPENAI_API_KEY="sua-chave"        # Windows PowerShell: $env:OPENAI_API_KEY="sua-chave"
python3 gerar.py "Cartaz com o texto VERêÆO 2027" --modelo sunburst --quality high --seco
python3 gerar.py "Logo de padaria, formas simples" --formato svg --fundo transparente
python3 gerar.py "Gato pisca e volta êÂ  pose inicial, cêÂ¢mera parada" --formato gif --quadros 9 --ms 200
python3 exemplos/baixar.py
python3 gerar.py "Pinte de azul o vaso no cêÂ­rculo. NêÂ£o mude mais nada. Tire o cêÂ­rculo." --editar exemplos/cozinha.webp --markup exemplos/circulo.png --complexity low
```

A chave da API êÂ© criada em https://platform.openai.com/api-keys e cobrada êÂ  parte da assinatura do ChatGPT.

No Windows, use `py` no lugar de `python3`. Sem Git, baixe o [ZIP](https://github.com/linnoff88-dev/gpt-image-26/archive/refs/heads/main.zip).

`python3 gerar.py --help` lista todas as opêÂ§êÂµes e os padrêÂµes (modelo `flare`, qualidade `medium`). Cada pedido real êÂ© cobrado na sua conta da OpenAI.

## Custo (calculadora oficial, imagem 1024êâ1024)

| Qualidade | GPT Image 2.5 | GPT Image 2.6 |
|---|---|---|
| low | US$ 0,006 | US$ 0,025 (4,2êâ) |
| medium | US$ 0,013 | US$ 0,044 (3,3êâ) |
| high | US$ 0,053 | US$ 0,053 (igual) |
| xhigh | US$ 0,094 | US$ 0,094 (igual) |
| max | US$ 0,211 | US$ 0,211 (igual) |

## Fontes

DocumentaêÂ§êÂ£o oficial da OpenAI, consultada em 07/11/2026:
[guia de prompts do GPT Image 2.6](https://developers.openai.com/api/docs/guides/image-prompting?model=gpt-image-2.6),
[geraêÂ§êÂ£o de imagem](https://developers.openai.com/api/docs/guides/image-generation) e
[preêÂ§os](https://developers.openai.com/api/docs/pricing).
As imagens de exemplo do guia sêÂ£o da documentaêÂ§êÂ£o da OpenAI.

---

Feito pelo [ARCKHê AI](https://ARCKHê AI).

---

<div align="center">
  <img src="capa/logo.svg" alt="Arckhé AI" height="32" />
  <p><strong>Arckhé AI</strong></p>
</div>