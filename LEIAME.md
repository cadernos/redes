# Kit de cards CadLin (Feed 4:5)

Conteúdo:
- `cadlin_cards.py`: gera todos os cards de um artigo, em todas as cores, a partir de um `spec.json`.
- `templates/Feed_4x5_Meta/`: os seis decks R02 limpos do Estúdio Guayabo (35 modelos cada; Neutro com 12). A numeração dos slides é a da Tabela de Modelos de Postagem.
- `fontes/`: Red Hat Display (8 pesos), instaladas automaticamente pelo script.
- `exemplo/`: spec de teste e imagem de teste.

Execução (dentro da pasta do kit):

    python3 cadlin_cards.py --spec spec.json --templates templates/Feed_4x5_Meta \
        --fonts fontes --out saida

Opcional: `--cores Azul,Verde` restringe as cores (padrão: Azul, Verde, Amarelo, Rosa, Lilas, Neutro).

Saída em `saida/<slug>_cards.zip`:
- `PNG/<Cor>/` com um PNG 1080×1350 por card, idioma e variante. Nome: `<slug>_<card>_M<modelo>-<slide>_<PT|EN>_<Cor>_<fundo-neutro|fundo-colorido>.png`
- `PPTX/` com um deck editável por cor
- `PAINEL_<Cor>.jpg` com miniaturas para a escolha do dia
- `RELATORIO.txt` com limites de caracteres excedidos e cards de imagem sem imagem

Marcação no spec: `{{termo}}` aplica a ênfase própria do modelo (itálico em títulos, negrito na massa de texto, grifo colorido em respostas e citações). `**termo**` força negrito (usado nas editorias). Colchetes simples, como `[...]` em citações, são texto literal.

Observação: os PNGs são renderizados pelo LibreOffice com as fontes corretas. Quebras de linha podem diferir em uma palavra das do PowerPoint; o PPTX acompanha para ajustes e exportação final, se necessário.
