# GPT Image 2.6 na prÃ¡tica

<div align="center">
  <img src="capa/logo.svg" alt="Arckhé AI" height="48" />
  <p><strong>Arckhé AI</strong></p>
</div>


[![GPT Image 2.6 na prÃ¡tica](guia/assets/banner.jpg)](https://inematds.github.io/gpt-image-26/guia/)

**ðŸ‡§ðŸ‡· [PortuguÃªs](README.md) Â· ðŸ‡ºðŸ‡¸ [English](README.en.md) Â· ðŸ‡ªðŸ‡¸ [EspaÃ±ol](README.es.md)**

## O que Ã©

O GPT Image 2.6 Ã© o modelo de imagem mais novo da OpenAI, que jÃ¡ roda dentro do ChatGPT e do Codex e tambÃ©m pode ser usado pela API. Este repositÃ³rio Ã© um guia para quem cria imagens para posts, anÃºncios, logos, histÃ³rias ou vÃ­deos e quer tirar proveito das novidades: o ajuste de complexidade (quanto o modelo planeja antes de desenhar), GIF animado, logo em vetor (SVG) e ediÃ§Ã£o sÃ³ na Ã¡rea que vocÃª marca. Para usar basta uma conta do ChatGPT; para a API, uma chave da OpenAI (cobrada Ã  parte da assinatura) e o script `gerar.py`, que sÃ³ precisa do Python.

## ðŸ“– Guia de uso

Guia completo (landing + passo a passo): **https://inematds.github.io/gpt-image-26/guia/**

ðŸŽ¬ VÃ­deo: https://www.youtube.com/watch?v=bHTe58nwW3s

## ConteÃºdo

| Arquivo | O que Ã© |
|---|---|
| `guia/` | PÃ¡gina do guia em PT, com `en/` e `es/` |
| `prompts.md` | 10 prompts prontos: estrutura, complexidade, instruÃ§Ãµes em sequÃªncia, cartaz, personagem, referÃªncia salva, GIF, SVG, markup e ediÃ§Ã£o |
| `gerar.py` | Atalho para a API (sÃ³ biblioteca padrÃ£o do Python): gera imagem, SVG ou GIF, ou edita com markup, jÃ¡ com `complexity` e `quality`; confere os limites antes de gastar |
| `exemplos/baixar.py` | Baixa a foto e o cÃ­rculo de exemplo da OpenAI para testar a ediÃ§Ã£o com markup |
| `tests/` | Testes do `gerar.py` sem chamar a API: `python3 -m unittest discover tests` |

## O processo, do inÃ­cio ao fim

| # | Passo | Comando | Quem faz |
|---|---|---|---|
| 1 | Escolher o modelo: Flare (rÃ¡pido) ou Sunburst (detalhe) | â€” | ðŸ§  vocÃª |
| 2 | Escrever o pedido em seÃ§Ãµes (cena, sujeito, detalhes, restriÃ§Ãµes, texto entre aspas) | `prompts.md` | ðŸ§  vocÃª |
| 3 | Ver o pedido sem gastar | `python3 gerar.py "<prompt>" --seco` | âš™ï¸ script |
| 4 | Gerar e comparar: primeiro a complexidade, depois a qualidade | `python3 gerar.py "<prompt>" --complexity high --quality medium` | âš™ï¸ script (API, cobrado na sua conta) |
| 5 | Conferir mÃ£o, proporÃ§Ã£o, reflexo, contagem e texto | â€” | ðŸ§  vocÃª |
| 6 | Editar uma coisa por vez (ou circular com markup) | `python3 gerar.py "<mudanÃ§a>" --editar exemplos/cozinha.webp --markup exemplos/circulo.png --complexity low` | âš™ï¸ script |

No ChatGPT os passos 3, 4 e 6 sÃ£o sÃ³ conversa: peÃ§a a imagem, o GIF ("sprite sheet 3x3 â€¦ em loop") ou o SVG.

## Uso rÃ¡pido da API

```bash
export OPENAI_API_KEY="sua-chave"        # Windows PowerShell: $env:OPENAI_API_KEY="sua-chave"
python3 gerar.py "Cartaz com o texto VERÃƒO 2027" --modelo sunburst --quality high --seco
python3 gerar.py "Logo de padaria, formas simples" --formato svg --fundo transparente
python3 gerar.py "Gato pisca e volta Ã  pose inicial, cÃ¢mera parada" --formato gif --quadros 9 --ms 200
python3 exemplos/baixar.py
python3 gerar.py "Pinte de azul o vaso no cÃ­rculo. NÃ£o mude mais nada. Tire o cÃ­rculo." --editar exemplos/cozinha.webp --markup exemplos/circulo.png --complexity low
```

A chave da API Ã© criada em https://platform.openai.com/api-keys e cobrada Ã  parte da assinatura do ChatGPT.

No Windows, use `py` no lugar de `python3`. Sem Git, baixe o [ZIP](https://github.com/inematds/gpt-image-26/archive/refs/heads/main.zip).

`python3 gerar.py --help` lista todas as opÃ§Ãµes e os padrÃµes (modelo `flare`, qualidade `medium`). Cada pedido real Ã© cobrado na sua conta da OpenAI.

## Custo (calculadora oficial, imagem 1024Ã—1024)

| Qualidade | GPT Image 2.5 | GPT Image 2.6 |
|---|---|---|
| low | US$ 0,006 | US$ 0,025 (4,2Ã—) |
| medium | US$ 0,013 | US$ 0,044 (3,3Ã—) |
| high | US$ 0,053 | US$ 0,053 (igual) |
| xhigh | US$ 0,094 | US$ 0,094 (igual) |
| max | US$ 0,211 | US$ 0,211 (igual) |

## Fontes

DocumentaÃ§Ã£o oficial da OpenAI, consultada em 07/11/2026:
[guia de prompts do GPT Image 2.6](https://developers.openai.com/api/docs/guides/image-prompting?model=gpt-image-2.6),
[geraÃ§Ã£o de imagem](https://developers.openai.com/api/docs/guides/image-generation) e
[preÃ§os](https://developers.openai.com/api/docs/pricing).
As imagens de exemplo do guia sÃ£o da documentaÃ§Ã£o da OpenAI.

---

Feito pelo [INEMA.CLUB](https://inema.club).

---

<div align="center">
  <img src="capa/logo.svg" alt="Arckhé AI" height="32" />
  <p><strong>Arckhé AI</strong></p>
</div>