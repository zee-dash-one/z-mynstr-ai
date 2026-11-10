# Vídeo com letra: custo, serviços e direitos

Pesquisa de 10/11/2026 (BRT). Não é parecer jurídico nem contábil. Preços de ferramentas conferidos nas páginas oficiais nesta data; valores em dólar não foram convertidos, conforme o padrão dos outros documentos. Estimativas de mão de obra em real.

**Conclusão em uma linha:** o vídeo com letra como está hoje no catálogo vende por menos do que custa. A saída não é escolher um SaaS melhor, é transformar o vídeo em pipeline próprio e vendê-lo como add-on, não como brinde dentro do Presente.

## 1. O problema de margem

No catálogo atual, o Presente custa R$49–59 e o Padrão custa R$39. Ou seja: o vídeo com letra e a dedicatória valem **R$10–20** de acréscimo.

Um vídeo com letra feito à mão consome de 15 a 25 minutos de edição. A R$50 por hora, isso dá **R$12–20 por vídeo**. O produto vende o vídeo por menos do que ele custa produzir, e ainda paga o motor de música, a curadoria humana e a taxa de pagamento.

Enquanto isso não for resolvido, o Presente é um desconto disfarçado, não um produto.

## 2. Rotas e custo por vídeo

| Rota | Ferramenta | Custo fixo | Custo por vídeo | Quando faz sentido |
| --- | --- | --- | --- | --- |
| A. Template manual | CapCut Pro ou Canva Pro | US$12–20/mês | R$12–20 (mão de obra) | Até 20 vídeos/mês, ou para validar |
| B. Pipeline próprio | ffmpeg + WhisperX, sem SaaS | R$0 | R$0,02–0,10 + 2 min de QA | Escala; combina com o orquestrador |
| C. Visualizer pronto | Specterr, Videobolt, Renderforest | US$16,50–49/mês | US$3,30–18 | Resultado bonito sem desenvolvimento |
| D. B-roll com IA | CapCut Seedance, Runway, Kling | variável | ~US$3,60 por 30 s | Apenas como upsell premium |

A rota C é a mais cara por vídeo entre as automatizadas: o Specterr Pro entrega 60 vídeos por ano a US$198, o que dá US$3,30 por vídeo, e o plano Unlimited custa US$49/mês. A rota D produz visual bonito e inconsistente, com custo por segundo, e não serve para produção em série.

## 3. Rota recomendada: pipeline próprio

O vídeo com letra é o mesmo problema que a música já resolveu: entrada estruturada, saída determinística. A letra existe em texto, com estrutura de verso e refrão. O áudio existe em MP3 normalizado.

### 3.1 Desenho em quatro etapas

1. **Alinhamento**: WhisperX roda local sobre o MP3 entregue e devolve timestamp por palavra.
2. **Legenda**: um gerador monta o arquivo `.ass` com a palavra destacada no tempo do áudio (efeito karaokê).
3. **Render**: ffmpeg queima a legenda sobre o fundo escolhido e exporta nos formatos de entrega.
4. **Moldura**: nome, data e dedicatória entram como camada fixa no mesmo render.

Custo marginal: segundos de CPU. Sem licença de SaaS, sem watermark, sem limite de exportação, sem depender de layout de terceiro.

### 3.2 Formatos de saída

- 1080×1920 (9:16) para Reels, Shorts e TikTok.
- 1920×1080 (16:9) para YouTube.
- 1080×1080 (1:1) opcional para feed.

## 4. Serviços, com preços verificados

| Camada | Serviço | Preço conferido |
| --- | --- | --- |
| Edição manual | CapCut Pro | US$19,99/mês (Ultra US$79/mês) |
| Edição manual | Canva Pro | US$144/ano |
| Edição manual | VEED | Creator US$12/mês no plano anual; Pro US$22/mês |
| Visualizer/letra pronta | Specterr | Grátis com marca e 1 vídeo/dia; Pro US$16,50/mês anual (US$198/ano, 60 vídeos); Unlimited US$49/mês; vídeo único US$14,99–29,99 |
| B-roll com IA | CapCut (Seedance) | a partir de US$0,12/s no Pro |
| Alinhamento de letra | WhisperX | gratuito, roda local |

## 5. Direitos em seis camadas

A música já está resolvida no mapa de motores. As outras cinco camadas são onde o vídeo morde.

| Camada | O que verificar | Armadilha concreta |
| --- | --- | --- |
| Música | Licença do motor permite uso comercial **e revenda ao cliente** | Suno só vale para download dentro da cota; Mureka, Lyria e ElevenLabs pagos, ok |
| Ferramenta de vídeo | Direito de **revender** o vídeo produzido | O Specterr exige plano customizado para revender vídeos feitos na ferramenta; o Pro não cobre |
| Fontes | Licença comercial de embed | Preferir Google Fonts (OFL). Fonte de biblioteca interna de CapCut ou Canva tem licença própria e limite de uso fora da plataforma |
| Imagens e fundos | Pexels e Pixabay permitem uso comercial, mas proíbem vender a cópia isolada | Foto de pessoa identificável no fundo é direito de imagem de terceiro |
| Fotos do cliente | O cliente precisa declarar que tem direito sobre as imagens enviadas | O Termo atual cobre texto, não imagem |
| Content ID | Não registrar as faixas no Content ID | Ao distribuir no Spotify via distribuidora, o Content ID pode reivindicar os vídeos dos próprios clientes |

O ponto central: **a licença entregue ao cliente precisa cobrir o vídeo explicitamente**. Hoje o certificado fala em faixa. Se o vídeo contém a faixa, a fonte e a foto da família, o escopo tem de listar os três; senão se entrega um vídeo com licença silenciosa.

## 6. Preço e posicionamento

Duas saídas possíveis, e elas não se excluem:

- **Automatizar primeiro** e manter o Presente com vídeo. Com pipeline próprio, o vídeo custa centavos e os R$10–20 de diferença viram margem.
- **Vender o vídeo como upsell pós-compra, a R$19–29.** Quem já recebeu a música é o cliente mais fácil de converter, e com pipeline próprio a margem passa de 90%.

O que não fazer: contratar editor freelancer a R$30–40 por vídeo no MVP. Isso queima a margem do Presente para validar algo que ainda não foi pedido.

## 7. Primeiros passos

1. Renderizar um vídeo de 60 s com WhisperX + ffmpeg e medir tempo de máquina e qualidade da sincronização em pt-BR.
2. Testar dois layouts fixos (um claro, um escuro) e decidir o padrão da marca.
3. Fazer o teste jurídico das licenças: Specterr (revenda), Pexels/Pixabay (fundo), Google Fonts (embed).
4. Definir se o vídeo entra no Presente ou vira add-on de R$19–29, com o teste A/B nos primeiros pedidos.

## 8. Método e limitações

- Preços lidos nas páginas oficiais em 10/11/2026, sem conversão cambial.
- Nenhuma ferramenta foi assinada, instalada ou testada.
- A estimativa de 2 a 3 minutos de QA por vídeo é hipótese, não medição.
- O tempo de desenvolvimento do pipeline (1 a 3 dias) é estimativa.
- As questões de licença precisam de leitura dos termos completos e, nos pontos de revenda, de validação jurídica.

## Fontes

- CapCut: https://www.capcut.com/pt-br/pricing
- Canva: https://www.canva.com/pt_br/precos/
- VEED: https://www.veed.io/pricing
- Specterr: https://specterr.com/pricing/
- WhisperX: https://github.com/m-bain/whisperX
- ffmpeg: https://ffmpeg.org/
