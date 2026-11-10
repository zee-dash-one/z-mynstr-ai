# Loja de micro-músicas com IA (Suno)
Documento do projeto, criado em 16/10/2026 (BRT). Não é parecer jurídico.

## 1. Resumo jurídico da Suno
- **Titularidade:** nos planos Pro e Premier, a Suno cede ao assinante os direitos que ela tiver sobre as faixas. Ela não garante que exista direito autoral.
- **Uso comercial:** vale só para faixas baixadas por um canal oficial, dentro da cota mensal do plano: 20 por mês no Pro e 60 no Premier.
- **Duração:** os direitos sobre as faixas já baixadas são perpétuos e continuam valendo depois de cancelar a assinatura.
- **Ceder a clientes:** dá para licenciar ou ceder as faixas. As restrições da Suno continuam valendo, e o Hil continua responsável perante a Suno pelo uso que o cliente fizer. Por isso, o contrato precisa repassar essas proibições.
- **Território:** os termos da Suno não trazem limite de território. Restringir o uso ao Brasil é uma cláusula do contrato com o cliente.
- **Lei brasileira:** pela Lei 9.610/98, art. 11, uma faixa 100% gerada por IA provavelmente não tem direito autoral. Só a parte humana, como letra e edição, pode ser protegida.
- **Recomendação:** oferecer uma licença de uso comercial perpétua, nunca exclusividade, e pedir a um advogado que revise o modelo de contrato e o Termo de Uso.

Fontes e detalhes: `/workspace/projetos/suno-direitos-autorais.md` e `/workspace/suno/`.

## 2. Riscos de mau uso e responsabilidade
- **Regra geral:** quem responde pelo mau uso é o comprador. O Hil só responde junto se tiver participado, por exemplo se gerou uma faixa ilícita a pedido do comprador.
- **Uso político:** quem recebe a punição do TSE é o candidato ou quem fez a propaganda.
- **Publicidade sem aviso de IA:** pelo CDC, a responsabilidade é do anunciante, ou seja, do comprador.
- **Imitar artista ou usar voz real:** o Hil e o comprador podem responder juntos (Código Civil, arts. 12, 20 e 942).
- **Difamação ou ódio:** se a letra ofensiva saiu do sistema do Hil a pedido do comprador, os dois podem ser processados juntos. Num caso extremo, o Hil pode ser coautor do crime.
- **Cópia de música que já existe:** a lei de direito autoral responsabiliza também quem vende, mesmo que o comprador tenha agido de boa fé.
- **Pior caso:** processo de indenização, de alguns milhares a dezenas de milhares de reais (estimativa, sem jurisprudência verificada), a Suno cobrando o Hil e ordem de retirada do conteúdo.
- **Criminal:** só com participação consciente.

Detalhes e fontes: `/workspace/suno/mau-uso-responsabilidade.md`.

## 3. Mapa das plataformas de música com IA
_Incorporado de `/workspace/suno/plataformas-musica-ia.md` em 16/10/2026, a pedido do Hil via Marketing._

Uso previsto: músicas personalizadas curtas (1–2 min), com voz em pt-BR, vendidas a R$20–50 com licença de uso (pessoal ou comercial). Como Hil revende a faixa, **todo uso conta como comercial**, então o plano grátis só serve para prévia ou rascunho (salvo exceções indicadas abaixo).
Legenda: **[oficial]** = página da própria empresa; **[terceiro]** = review/comparador (confirmar no checkout); **[não confirmado]** = não achei fonte confiável. Preços em US$/€, sem conversão. A qualidade da voz em pt-BR **não foi testada por mim** em nenhuma delas: onde houver, cito só o que a fonte diz sobre suporte ao idioma.

### 1. Músicas completas com voz e letra

### Suno (referência: swot-micromusicas.md)
- Grátis: ~10 músicas/dia, só uso não comercial [terceiro]. Pro ~US$10/mês com **20 downloads comerciais/mês**; Premier ~US$30/mês com **60/mês** (desde 03/09/2026). Só vale comercialmente a faixa baixada dentro da cota [oficial].
- Titularidade: no Pro/Premier a Suno cede o Output a você. Direito perpétuo sobre as faixas baixadas.
- pt-BR: usado na pesquisa anterior, mas sem teste formal. Duração máxima: [não confirmado].
- API: **não há oficial**. As "APIs Suno" de terceiros violam os Termos, então evitar.
- Fontes: https://help.suno.com/en/articles/13876865 · https://suno.com/terms · https://suno.com/pricing

### Udio
- Standard US$10 e Pro US$30/mês [terceiro]. **Downloads desativados em todos os planos desde out/2025** (acordo com a UMG), sem data de retorno. A saída é só para uso pessoal, a Udio fica com a titularidade e treina com o que você gera [terceiro].
- **Não serve para o negócio hoje.**
- Fontes: https://saasinspector.com/compare/mureka-vs-udio · https://undetectr.com/blog/mureka-ai-review

### Mureka (Kunlun/SkyMusic)
- Grátis: 4 músicas/dia no modelo v7.5, sem download e sem direito comercial, com crédito à Mureka.
- Pro US$10/mês (US$8 no anual): 5.000 Gold, "até 500 músicas", **downloads MP3 ilimitados** e direito comercial pleno, inclusive sobre faixas antigas.
- Premier US$30 (US$24 no anual): 20.000 Gold, WAV, 12 stems, MIDI e clonagem de voz [oficial + terceiro].
- Titularidade: sua nos planos pagos [terceiro]. Restrições: há um processo nos EUA sobre os dados de treino, e o vídeo exportado sai com marca d'água mesmo no plano pago [terceiro].
- pt-BR, duração máxima e API pública: [não confirmado].
- Fontes: https://www.mureka.ai/subscribe · https://undetectr.com/blog/mureka-ai-review · https://meikuio.com/best-ai-music-generators/

### Producer.ai (ex-Riffusion, hoje Google Flow Music)
- Comprada pelo Google em 24/02/2026 e roda o Lyria 3.
- Grátis: créditos limitados, uso pessoal com atribuição.
- Pagos: Starter US$8 (3.000 créditos), Plus US$24 (10.000) e Member US$64 (30.000). O direito comercial nos pagos é "intended" e **[não confirmado]** [terceiro].
- Titularidade: o output é seu, mas o Google mantém uma licença ampla e perpétua, inclusive para treino [terceiro].
- pt-BR: herda o Lyria, que suporta português.
- Fontes: https://www.theverge.com/tech/883307/google-producerai-deal-music · https://www.documentarytube.com/blog/producerai-joined-google-heres-what-google-flow-music-can-actually-do/

### Google Lyria 3 / 3.5 (app Gemini + API)
- App Gemini, grátis: faixas de 30 s, limite diário não publicado.
- App Gemini, pago: Lyria 3 Pro gera **até 3 min**. Plus 10/dia, Pro 20/dia, Ultra 50/dia [terceiro].
- Comercial: permitido em assinatura paga, API paga ou Vertex. O grátis em geral não é comercial [terceiro].
- **API oficial:** Lyria 3.5 a **US$0,08 por música completa**; Lyria 3 Clip a US$0,04 por clipe de 30 s. Sem free tier na API [oficial].
- **pt-BR oficialmente suportado:** basta escrever o prompt em português que o modelo adapta a pronúncia [oficial].
- Fontes: https://ai.google.dev/gemini-api/docs/pricing · https://ai.google.dev/gemini-api/docs/music-generation · https://docs.cloud.google.com/gemini-enterprise-agent-platform/models/lyria/lyria-3 · https://9to5google.com/2026/03/25/gemini-lyria-3-pro/

### ElevenLabs Music (Hil já tem o conector)
- Gasta 900 créditos por minuto, de um pool compartilhado com TTS etc. [oficial].
- Free: 10.000 créditos, até 11 min/mês, **sem download**, não comercial.
- Starter: US$6/mês, 30.000 créditos (~30 min de geração e download).
- Creator: US$22, 121.000 créditos (US$11 no 1º mês).
- Pro: US$99.
- Comercial: permitido em todos os planos pagos, exceto cinema, TV, rádio e games de estúdio. Distribuição em streaming só a partir do Creator [oficial]. Faixas geradas no plano pago continuam liberadas depois que você cancela [oficial].
- Duração de 3 s a 5 min, "vozes em vários idiomas". O pt-BR específico está **[não confirmado]** [terceiro].
- Treino com dados licenciados (Merlin, Kobalt etc.) [terceiro].
- API oficial: ~US$0,15/min na v2.5 [terceiro]. Atenção: recursos "Beta" não têm licença comercial [oficial].
- Fontes: https://elevenlabs.io/pricing · https://elevenlabs.io/music-terms · https://help.elevenlabs.io/hc/en-us/articles/13313564601361 · https://www.teamday.ai/blog/best-ai-music-models-2026

### Tunee
- Agente que roteia entre Mureka, MiniMax, TemPolor e ACE-Step.
- Free: a Tunee é dona da faixa, e o uso é não comercial com atribuição [oficial].
- Pagos: Basic/Plus/Pro, que segundo um terceiro custam US$18, US$38 e US$89/mês, com ~180, ~400 e ~1.150 músicas.
- Comercial e titularidade perpétuos no pago, e dá para "desbloquear" faixas antigas do free: 1/mês no Basic e no Plus, 3/mês no Pro [oficial].
- pt-BR, duração e API: [não confirmado]. Há uma camada de "Skills" para agentes [terceiro].
- Fontes: https://www.tunee.ai/faq · https://aitrustlist.com/ai/tunee

### Sonauto (agora Treblo)
- **App grátis, ilimitado, e os Termos cedem a música a você com uso comercial permitido mesmo no grátis** [terceiro, citando ToS]. Confirmar no ToS antes de vender.
- API paga: a partir de US$11/mês (20.000 créditos) [terceiro]. Também está na fal.ai por US$0,075/geração [terceiro].
- pt-BR e duração: [não confirmado]. Um review dá nota baixa de capacidade (52,2) [terceiro].
- Fontes: https://treblo.com/tos · https://treblo.com/blog/sonauto-is-now-treblo · https://treblo.com/api-terms · https://vouchaitools.com/tools/music-generators/treblo

### MiniMax Music
- **API paga fechada para novos usuários desde 20/08/2026, e as APIs grátis foram descontinuadas** [oficial]. O app MiniMax Audio continua existindo, mas o plano e o direito comercial dele estão [não confirmado].
- Pesos abertos do MiniMax Music 3 (Community License): uso comercial ok, mas exige exibir "MiniMax-Music3" no produto e pedir autorização acima de US$20M/ano [terceiro].
- Fontes: https://platform.minimax.io/docs/pricing/overview · https://www.teamday.ai/blog/best-ai-music-models-2026

### Stable Audio (Stability)
- Free: 50 créditos/mês, pessoal. Solo: US$12/mês, 660 créditos, comercial [terceiro].
- Pesos abertos: comercial grátis até US$1M/ano de receita [terceiro].
- Foco instrumental e efeitos. Voz com letra em pt-BR: [não confirmado], provavelmente fraca. Na fal, até 190 s por US$0,20 [terceiro].
- Fonte: https://undetectr.com/blog/stable-audio-review

### Open source (rodar local ou via fal.ai)
- **ACE-Step 1.5:** licença **MIT**. O model card diz que dá para usar comercialmente e que foi treinado com dados licenciados ou royalty-free.
  - Suporta letras em 50+ idiomas, **incluindo português** (vocal_language="pt").
  - Roda com menos de 4 GB de VRAM. A equipe diz que a qualidade fica "entre Suno v4.5 e v5" (afirmação do próprio autor).
  - Na fal: US$0,0002/s, ~83 min por US$1 [terceiro].
  - Ainda há um pedido de esclarecimento sobre os termos do output em aberto (Discussion #1256).
  - Fontes: https://github.com/ace-step/ACE-Step-1.5 · https://huggingface.co/ACE-Step/Ace-Step1.5 · https://fal.ai/learn/tools/ai-music-generators
- **YuE:** Apache-2.0, comercial permitido [terceiro]. pt-BR e qualidade: [não confirmado].
- **Meta MusicGen/AudioCraft:** não pesquisei nesta rodada. Até onde sei, gera só instrumental e os pesos são não comerciais (CC-BY-NC): **[não confirmado]**.

### Outros apps de "música completa"
- **Boomy:** a partir de US$9,99, Pro US$29,99. O comercial só vale no pago. A Boomy fica com o copyright ou faz co-titularidade (comprar o copyright exige pedido manual). O free não tem download [terceiro]. https://aitrendtool.com/best/best-ai-music-generators-for-commercial-use
- **Musicful:** Free/Basic são não comerciais; Standard, Pro e Perpétuo são comerciais [oficial]. Preços: [não confirmado]. https://www.musicful.ai/pricing/
- **TopMediai:** de US$4,99/semana (1.500 créditos) a US$199,99/ano (60.000), com certificado PDF de licença; o free é só pessoal [oficial]. Muitas dessas ferramentas rodam modelos de terceiros por baixo [não confirmado]. https://www.topmediai.com/pricing/
- **Tad AI e Musci.io:** aparecem num comparador (Tad Standard US$7,99 com ~50 músicas; Musci Standard US$29,99 com ~600) [terceiro]. https://songcreator.pro/blog/ai-music-generator-pricing

### 2. Só instrumental (fundo, versão "sem voz")
- **Mubert:**
  - Free tem 25 faixas e 5 downloads, não comercial; Creator US$14, não comercial; Pro US$39, comercial; Business US$199.
  - **Proibido distribuir em streaming e registrar em Content ID.** A Mubert é dona e só licencia [oficial].
  - Tem API sob consulta. https://mubert.com/render/license
- **Soundraw:**
  - Creator US$16,99/mês (~US$11 no anual), com licença de música de fundo; Artist divide a titularidade 50/50.
  - Licença permanente. Content ID proibido [terceiro]. https://sonilo.com/help/licensing/ai-music-generator-licenses-compared
- **AIVA:**
  - Free é não comercial com atribuição. Standard €11/mês no anual, 15 downloads, monetização limitada.
  - **Pro €33/mês no anual, 300 downloads, copyright cedido a você** [terceiro]. Mesma fonte acima.
- **Beatoven.ai:**
  - A partir de US$6/mês. Cada download vem com licença comercial perpétua e não exclusiva; a Beatoven mantém a titularidade e não permite lançamento avulso em streaming.
  - Na fal, US$0,10/requisição [terceiro]. https://aitrendtool.com/best/best-ai-music-generators-for-commercial-use

### 3. Roteamento sugerido

| Necessidade | Rota principal | Por quê | Fallback |
|---|---|---|---|
| Prévia grátis pro cliente (não é a entrega) | Treblo/Sonauto grátis (ilimitado), ou ACE-Step local | Custo zero. O Treblo permite comercial até no free (confirmar ToS) | Gemini grátis (clipe de 30 s), Mureka free (4/dia, só ouvir) |
| Faixa final paga em pt-BR, volume | **Mureka Pro US$10** (downloads ilimitados, comercial) | Sem o teto de 20/60 da Suno | Lyria 3.5 via API (US$0,08/música, pt-BR oficial) |
| Faixa final "premium" ou cliente exigente | Suno Pro/Premier (gasta cota só com a versão aprovada) | Melhor percepção de qualidade, mas a cota é curta | ElevenLabs Creator (licenciado, até 5 min) |
| Automação por API (checkout → geração) | **Lyria 3.5 API** ou **ElevenLabs Music API** (conector já existe) | APIs oficiais, comercial no pago | ACE-Step na fal.ai (centavos) ou self-host |
| Instrumental / versão sem voz | Beatoven (US$6) ou Mureka Premier (stems) | Licença comercial por download | AIVA Pro, se quiser copyright cedido |
| Cota acabou no mês | Mureka → Lyria API (pay-per-use) → ACE-Step | Pay-per-use não tem teto | Tunee (multimodelo) |
| **Não usar** | Udio (sem download), MiniMax API (fechada), Mubert e Boomy (licença restrita para revenda) | — | — |

Regra de ouro: só entregar a faixa gerada **dentro de um plano pago** ou com licença que permita comercial (Treblo e ACE-Step são as exceções, a confirmar). Guardar plano, data e ID de cada faixa como prova.

### 4. O que assinar primeiro
1. **Mureka Pro (US$10/mês):** é o único plano barato com download ilimitado e direito comercial pleno, e resolve o gargalo da cota da Suno. Antes de assinar, testar a voz em pt-BR no free (4/dia).
2. **Lyria 3.5 via API do Gemini (pay-per-use, US$0,08/música):** não tem mensalidade, o pt-BR é oficial e já serve para automação.
3. **ElevenLabs:** se o plano atual do Hil for pago, a Music já está liberada para uso comercial. Ver o plano do conector antes de gastar mais. Subir para o Creator (US$22) só se precisar de streaming ou de mais minutos.
4. Suno Pro/Premier só como linha "premium", se o teste cego mostrar qualidade claramente superior em pt-BR.

### Pendências e lacunas
- Teste de qualidade em pt-BR (mesma letra em Mureka, Lyria, ElevenLabs, Suno, ACE-Step e Treblo): não feito.
- Confirmar no ToS: o comercial grátis do Treblo; o comercial no pago e a licença do Google no Producer.ai/Flow Music; os preços da Tunee e da Musicful; a duração máxima de Mureka e Suno.
- Meta MusicGen e YuE: os detalhes não foram verificados.
- Custo real de prévia gratuita por lead e taxa de conversão prévia → pedido: medir nos primeiros pedidos-piloto (ver analise-concorrente-hosannasong.md §9).
