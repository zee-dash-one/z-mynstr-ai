Plataforma de Micro-Músicas com IA Agêntica
Documento de requisitos e plano de projeto · v2.1 · 10/11/2026 (BRT)
Evolução do documento «Loja de micro-músicas com IA (Suno)». Consolida o resumo jurídico, a análise de riscos e o mapa de plataformas, e acrescenta produto, arquitetura agêntica, requisitos, operação e roadmap. A v2.1 incorpora a análise do concorrente direto (analise-concorrente-hosannasong.md) e passa a prévia cantada gratuita a requisito de produto. Não é parecer jurídico nem contábil: itens marcados com [VALIDAR] dependem de confirmação com advogado, contador ou termos vigentes.
1. Visão e proposta de valor
Visão: uma loja online que vende músicas curtas (1–2 min), personalizadas, com letra e voz em português do Brasil, entregues em horas e não em dias, com custo de produção baixo graças a agentes de IA que cuidam do atendimento, da letra, da geração, da curadoria e da entrega, com o Hil como aprovador final nas fases iniciais.
Proposta ao cliente: «Conte sua história em 3 minutos, receba sua música pronta no mesmo dia, com licença de uso clara.»
Diferenciais:
• Briefing guiado por agente (WhatsApp ou site), sem formulário longo.
• Letra aprovada pelo cliente antes de gastar geração de música.
• Curadoria humana final: nada sai sem ouvir (MVP).
• Licença comercial perpétua e não exclusiva, com certificado em PDF e rastreabilidade de cada faixa.
• Múltiplos motores de música com roteamento por custo e qualidade, sem depender de um único fornecedor.
• Prévia cantada grátis de 30 s antes do pagamento, apenas nos produtos de 2 min, com a letra já aprovada [validado no concorrente direto; ver analise-concorrente-hosannasong.md].
• Licença comercial perpétua com certificado em PDF, e não apenas licença pessoal de presente.
Fora de escopo (por ora): exclusividade de obra, registro de direito autoral de faixa 100% IA, clonagem de voz de pessoas reais, cobertura de músicas existentes, venda para cinema, TV, rádio ou games de estúdio, distribuição em streaming em nome do cliente.
2. Público, produtos e preço
Públicos iniciais: (1) presentes e datas (aniversário, casamento, formatura, Dia das Mães, declarações); (2) pequenos negócios (jingle simples, vinheta para redes sociais); (3) criadores de conteúdo (trilha com voz para vídeos). A hipótese principal é o público 1, que aceita o preço de R$20–50 e dispensa contrato complexo.
Catálogo inicial (hipóteses a validar com pedidos reais):
Produto
Conteúdo
Preço sugerido
Revisões
Mini
até 1 min, letra curta, 1 estilo, versão para Reels e Shorts (sem prévia cantada)
R$20–25
1
Padrão
até 2 min, letra completa, capa simples
R$39
2
Presente
Padrão + vídeo com letra e dedicatória
R$49–59
2
Negócio
Padrão + versão instrumental + licença comercial ampliada
R$79–149 [VALIDAR]
2
Posicionamento de preço [DECIDIR]: o piso do mercado de música personalizada já está em R$49,90 com prévia cantada grátis e duas versões (analise-concorrente-hosannasong.md §3). Não competir por preço: cobrar pela licença comercial, pelo certificado e pela aprovação humana, que os concorrentes diretos não oferecem. A faixa de R$39 do produto Padrão tende a ficar abaixo do valor percebido e deve ser reavaliada à luz do teste cego e dos primeiros pedidos. A prévia cantada fica restrita aos produtos de 2 min e passa a funcionar como argumento de upgrade: quem quer ouvir antes escolhe o produto em que a margem está. O Mini, de 1 min, atende Reels e Shorts com preço menor e sem prévia, porque numa faixa de 1 min qualquer prévia relevante entregaria quase o produto inteiro. O Mini fica em R$20–25 para abrir R$14 de degrau até o Padrão.

Regras de oferta: prazo-alvo de entrega de 24 h no MVP; revisão limitada a ajustes de letra, ritmo ou estilo (não troca total de tema); reembolso se a entrega falhar ou se o resultado não corresponder ao briefing aprovado, nos termos do Termo de Uso.
Economia unitária (estimativa, sem conversão cambial): o custo de motor por faixa final é baixo porque cada faixa consome em média 3–6 gerações. Referências: Lyria 3.5 via API a US$0,08 por música; Mureka Pro a US$10/mês com até 500 músicas; Suno Pro a US$10 por 20 downloads comerciais (cerca de US$0,50 por faixa baixada); ElevenLabs a 900 créditos por minuto. Os custos relevantes tendem a ser tempo humano de curadoria, taxas de pagamento, impostos e reembolsos, e não o motor. [VALIDAR com 20–30 pedidos reais] Com a prévia gratuita nos produtos de 2 min, cada interessado consome ao menos uma geração adicional, convertendo ou não. A prévia precisa rodar em motor de custo marginal próximo de zero e com licença comercial por geração (ACE-Step, Treblo ou Lyria a US$0,08); nunca em motor com cota por download.
3. Jornada do cliente
1. Descoberta: landing page, Instagram, WhatsApp, indicação.
2. Pedido: escolhe o produto e informa nome, ocasião, e-mail e WhatsApp; aceita o Termo de Uso e a Política de Privacidade (checkbox registrado).
3. Briefing: o agente de atendimento conversa por WhatsApp ou web e coleta ocasião, pessoas, memórias, nomes, palavras que devem aparecer, estilo, humor, voz (feminina, masculina, neutra) e o que evitar.
4. Letra: o agente propõe a letra; o cliente lê, edita e aprova (limite de rodadas por produto).
5. Prévia gratuita (só nos produtos de 2 min): com a letra aprovada e o compliance liberado, o sistema gera 30 s da música cantada com o nome do homenageado e libera sem cartão. A prévia não é a entrega e não é baixável. O Mini de 1 min não tem prévia cantada.
6. Pagamento: Pix primeiro; cartão como segunda opção. A geração da faixa completa só começa após confirmação do pagamento (webhook).
7. Produção: agentes geram candidatas, curam e escolhem a melhor.
8. Aprovação interna: o Hil ouve e aprova (MVP).
9. Entrega: link privado com player, download MP3, certificado de licença, capa e (se contratado) vídeo.
10. Revisão e pós-venda: pedido de ajuste, avaliação, cupom de indicação, lembrete de datas futuras.
4. Arquitetura agêntica
Princípio: um orquestrador determinístico (máquina de estados) chama agentes especializados com entradas e saídas estruturadas (JSON). Agentes não decidem sozinhos sobre pagamento, reembolso, entrega final ou conteúdo sensível; essas decisões passam por regras fixas ou por aprovação humana.
Agente
Função
Entrada → Saída
Guardrails
Atendimento/Briefing
Conversa, tira dúvidas, coleta o briefing
mensagens → briefing estruturado
Não promete prazo ou preço fora da tabela; não coleta dados sensíveis desnecessários; escala para humano se o cliente pedir ou houver reclamação
Compliance (pré-produção)
Analisa o briefing e a letra
briefing/letra → aprovado, ajustar ou bloqueado + motivo
Bloqueia política eleitoral, ódio, difamação, nomes de artistas ou imitação de voz, conteúdo sexual com menores, trechos de letras protegidas; roda antes da prévia gratuita e antes da geração final
Letrista
Escreve letra em pt-BR
briefing + estilo → letra com estrutura (verso, refrão) e métrica para a duração
Letra original; sem citar músicas existentes; respeita limite de palavras por duração
Diretor musical
Define prompt de estilo, andamento e voz; escolhe o motor
letra + produto + orçamento → plano de geração
Não usa nome de artista no prompt; segue a tabela de roteamento (seção 6)
Gerador
Executa a geração no motor (API ou fila para operador), inclusive a prévia antes do pagamento
plano → N candidatas com metadados + 1 prévia
Registra motor, versão, plano, data, ID e prompt de cada faixa, inclusive da prévia
QA/Curadoria
Analisa as candidatas
áudio + letra → ranking e checklist
Verifica duração, clipping, silêncio, pronúncia de nomes, aderência à letra, artefatos; transcreve o áudio e compara com a letra
Entrega
Monta pacote final
faixa aprovada → página de entrega, PDF de licença, capa, e-mail ou WhatsApp
Só dispara após aprovação humana (MVP)
Pós-venda
Revisões, avaliação, reativação
feedback → ação
Respeita limite de revisões; aciona o Hil em reembolso
Observador (opcional)
Monitora custo, filas e falhas
métricas → alertas
Alerta de custo diário e de fila parada
Estados do pedido: RASCUNHO → BRIEFING → LETRA_PROPOSTA → LETRA_APROVADA → PREVIA_GERANDO → PREVIA_ENVIADA → AGUARDANDO_PAGAMENTO → PAGO → GERANDO → CURADORIA → APROVAÇÃO_INTERNA → ENTREGUE → EM_REVISÃO → CONCLUÍDO; desvios: BLOQUEADO_COMPLIANCE, CANCELADO, REEMBOLSADO, EXPIRADO (prévia sem pagamento).
Abstração de motor: interface única MusicEngine com generate(lyrics, style, duration, voice, language), preview(lyrics, style, voice), status(), fetch_audio(), cost() e license_meta(). Cada motor é um adaptador. Motores sem API oficial (Suno, Mureka, provavelmente) operam em modo assistido: o agente prepara o prompt e a letra, o operador gera no site e envia o arquivo para a plataforma, que registra plano, data e ID. APIs de terceiros não oficiais da Suno ficam proibidas (violam os Termos). A prévia gratuita só roda em motor cuja licença comercial valha por geração, não por download, e nunca é o arquivo entregue.
5. Requisitos funcionais
5.1 Loja e pedido
• RF-01: landing page com catálogo, exemplos de áudio, FAQ e prazo de entrega.
• RF-02: checkout com Pix e cartão; geração de cobrança e confirmação por webhook.
• RF-03: aceite do Termo de Uso e da Política de Privacidade, registrado com data, hora, IP e versão do documento.
• RF-04: cupons de desconto e código de indicação.
• RF-05: nota fiscal ou recibo automático [VALIDAR enquadramento fiscal com contador].
5.2 Atendimento e briefing
• RF-06: atendimento por WhatsApp e por chat web, com o mesmo estado de conversa [VALIDAR política vigente da Meta para bots de IA].
• RF-07: briefing estruturado com campos obrigatórios (ocasião, nomes, estilo, voz, duração, palavras obrigatórias e proibidas).
• RF-08: o cliente pode enviar áudio de voz ou texto; áudios são transcritos.
• RF-09: transferência para humano em qualquer ponto, com histórico completo.
5.3 Letra e música
• RF-10: geração de letra em pt-BR com estrutura e métrica compatíveis com a duração do produto.
• RF-11: aprovação de letra pelo cliente antes de qualquer geração de música, inclusive da prévia; versões da letra guardadas.
• RF-12: roteamento automático de motor conforme a seção 6, com fallback e limite de custo por pedido.
• RF-13: geração de múltiplas candidatas (padrão: 3–4) e ranking automático.
• RF-14: checagem de qualidade automatizada: duração, nível de áudio, silêncio, transcrição versus letra, nomes próprios pronunciados corretamente.
• RF-15: painel do operador para ouvir candidatas, aprovar, pedir nova geração ou editar o prompt.
• RF-16: fluxo assistido para motores sem API: baixar contexto (prompt + letra), subir o arquivo gerado com plano, data e ID.
• RF-17: pós-processamento: normalização de volume, fade-out, corte de silêncio, MP3 320 kbps e versão WAV se o produto incluir.
• RF-18: geração de capa simples e vídeo com letra sincronizada; no Presente o vídeo está incluído e, nos demais produtos, é add-on pago de R$19–29 [fase 2; ver video-com-letra.md].
5.4 Entrega, licença e pós-venda
• RF-19: página de entrega privada, com link assinado e expiração configurável, player e download.
• RF-20: certificado de licença em PDF por faixa: cliente, produto, motor, plano, data, ID, escopo de uso, restrições repassadas da Suno ou do motor, território, cláusula de uso responsável.
• RF-21: solicitação de revisão dentro do limite do produto, com contagem automática.
• RF-22: avaliação (nota e comentário) e pedido de depoimento com autorização para uso do áudio como exemplo.
• RF-23: fluxo de reembolso com aprovação humana.
5.5 Administração
• RF-24: painel de pedidos com filtros por estado, prazo e motor.
• RF-25: fila de aprovações pendentes e alertas de atraso.
• RF-26: registro de auditoria de cada faixa (prompt, versão do motor, plano, data, ID, custo).
• RF-27: controle de cota mensal por motor (ex.: 20 downloads comerciais da Suno Pro) com bloqueio ao atingir o limite.
• RF-28: relatórios de receita, custo por faixa, margem, taxa de revisão e reembolso.
• RF-29: integração com ClickUp para tarefas manuais e com a agenda para prazos [opcional].
5.6 Prévia gratuita (pré-venda)
• RF-30: gerar prévia cantada de 30 s, nunca mais de 40% da faixa, a partir da letra aprovada, com o nome do homenageado, antes de qualquer pagamento e sem exigir cartão. A prévia existe apenas nos produtos de 2 min; o Mini de 1 min não tem prévia cantada.
• RF-31: a prévia passa pelo mesmo gate de compliance da entrega; conteúdo bloqueado não gera prévia nem chega ao cliente.
• RF-32: limite de prévias por visitante, por IP e por dia, com bloqueio automático, para conter custo de motor e abuso.
• RF-33: a prévia não é entregável: sai sem download, com corte ou marca sonora discreta, e o arquivo é descartado quando o pedido expira.
• RF-34: registrar custo, motor e conversão de cada prévia, para medir custo por lead e taxa prévia → pedido.
• RF-35: no Mini, compensar a ausência de prévia cantada com letra editável e aprovada, amostra de voz e estilo do catálogo, prazo e garantia de 7 dias explícitos na oferta.
5.7 Vídeo com letra
• RF-36: renderizar o vídeo por pipeline próprio (alinhamento por palavra, legenda .ass e ffmpeg), em 9:16 e 16:9, sem depender de SaaS com limite de exportação ou cláusula de não revenda.
• RF-37: registrar no vídeo a proveniência de cada camada (motor do áudio, fonte, banco de imagens e licença correspondente).
• RF-38: aceitar foto enviada pelo cliente somente com declaração de direito de uso, registrada com data e versão do termo.
• RF-39: o certificado do vídeo deve listar faixa, vídeo, fonte e imagem, com escopo de uso próprio, e não apenas a faixa.
• RF-40: não registrar as faixas em Content ID, para não reivindicar depois os vídeos dos próprios clientes.
6. Motores de música e roteamento
Baseado no mapa de 16/10/2026. Os preços e termos mudam com frequência: o sistema deve guardar os dados de cada motor em configuração, e a revisão dos termos deve ocorrer mensalmente.
Necessidade
Rota principal
Fallback
Observação
Prévia grátis (não é a entrega)
Treblo/Sonauto, ACE-Step local ou Lyria API
Gemini grátis (30 s)
Custo marginal próximo de zero e licença comercial por geração; confirmar no ToS antes de usar
Faixa final padrão em pt-BR
Mureka Pro
Lyria 3.5 API
Testar a voz em pt-BR no plano grátis antes de assinar
Faixa premium
Suno Pro/Premier, só com a versão aprovada
ElevenLabs Creator
Cota curta: 20 ou 60 por mês
Automação por API
Lyria 3.5 ou ElevenLabs Music
ACE-Step na fal.ai ou self-host
APIs oficiais com uso comercial no plano pago
Instrumental
Beatoven ou Mureka Premier
AIVA Pro
Licença comercial por download
Cota esgotada
Mureka → Lyria API → ACE-Step
Tunee
Pay-per-use sem teto
Não usar: Udio (sem download), MiniMax API (fechada para novos usuários), Mubert e Boomy (licença restrita para revenda), APIs não oficiais da Suno.
Regras do roteador: (1) só entregar faixa gerada em plano pago ou com licença comercial confirmada; (2) respeitar o teto de custo por pedido; (3) preferir o motor com melhor nota no teste cego para o estilo pedido; (4) se um motor falhar duas vezes, usar o fallback e registrar; (5) nunca misturar prompts com nomes de artistas; (6) a prévia gratuita roda em motor de custo marginal próximo de zero e nunca consome cota de download comercial; (7) a prévia e a faixa final podem vir de motores diferentes, mas a diferença de voz precisa ser aceitável para o cliente.
Teste cego obrigatório (Fase 0): mesma letra e mesmo briefing em Mureka, Lyria, ElevenLabs, Suno, ACE-Step e Treblo; no mínimo 5 avaliadores; critérios: pronúncia em pt-BR, naturalidade da voz, aderência ao estilo, ausência de artefatos, emoção percebida. O resultado define a rota principal.
7. Requisitos jurídicos e de compliance
7.1 Licença ao cliente
• RJ-01: oferecer licença de uso perpétua e não exclusiva; nunca prometer exclusividade nem direito autoral sobre a parte gerada por IA (Lei 9.610/98, art. 11: faixa 100% IA provavelmente não tem autoria protegida) [VALIDAR].
• RJ-02: repassar ao cliente as restrições dos motores (uso só de faixas baixadas por canais oficiais e dentro da cota; proibições de uso político, ilícito etc.), porque o Hil continua responsável perante o fornecedor.
• RJ-03: restringir o território ao Brasil por cláusula contratual, se desejado (os termos da Suno não limitam território).
• RJ-04: informar de forma transparente que a música é gerada por IA e que o cliente deve sinalizar isso quando a lei, a plataforma ou a campanha exigirem.
7.2 Conteúdo proibido (bloqueio automático e revisão humana)
• Propaganda eleitoral e conteúdo político-partidário.
• Difamação, discurso de ódio, assédio, conteúdo sexual envolvendo menores, apologia de crime.
• Imitação de artista, voz de pessoa real ou uso de marca de terceiros sem autorização.
• Reprodução ou paráfrase próxima de letra existente.
• Publicidade enganosa ou de produtos regulados sem autorização do cliente.
7.3 Responsabilidade
• RJ-05: Termo de Uso que atribua ao comprador a responsabilidade pelo uso, com cláusula de indenização, mas ciente de que o Hil pode responder solidariamente se participou da geração do conteúdo ilícito (Código Civil, arts. 12, 20 e 942). Por isso, o filtro de compliance faz parte do produto e não é opcional.
• RJ-06: guardar prova por 5 anos [VALIDAR]: briefing, aceite, prompt, ID e plano do motor, data, versão da letra aprovada, e-mails de entrega.
• RJ-07: processo de notificação e retirada (canal de contato para reclamações com prazo de resposta definido).
7.4 Consumidor e dados
• RJ-08: CDC: informações claras, prazo, política de revisão e reembolso; direito de arrependimento em compra online (art. 49) com exceção para produto personalizado a ser avaliado por advogado [VALIDAR].
• RJ-09: LGPD: base legal por finalidade, política de privacidade, minimização (coletar só o necessário), retenção definida, exclusão a pedido, cuidado com dados de menores e com histórias pessoais; controlar quais fornecedores de IA recebem dados do cliente.
• RJ-10: revisão por advogado do modelo de contrato, do Termo de Uso, da Política de Privacidade e do certificado de licença antes do lançamento.
7.5 Oferta e publicidade
• RJ-11: preço riscado, "de/por" e percentual de economia só com preço anterior real e praticado; é vedado somar extras avulsos para inflar a âncora (CDC, art. 37, §1º).
• RJ-12: notas e depoimentos devem ser verificáveis e, de preferência, hospedados em plataforma independente (Google, Reclame Aqui, Trustpilot). Selo "cliente verificado" emitido pelo próprio site não substitui prova.
• RJ-13: não prometer "100% de satisfação" nem garantia incondicional sem processo definido de reescrita e reembolso por trás da promessa.
• RJ-14: a licença e o certificado devem cobrir explicitamente o vídeo e as camadas que ele contém (faixa, fonte, imagem de fundo e foto do cliente), e não apenas a faixa.
Pior caso conhecido: indenização de alguns milhares a dezenas de milhares de reais (estimativa sem jurisprudência verificada), cobrança pela Suno e ordem de retirada. Mitigação: filtros, cota controlada, termos claros e seguro/reserva financeira [VALIDAR].
8. Requisitos não funcionais
• Desempenho: resposta do agente em até 5 s; pedido pago iniciado em até 1 min; entrega-alvo de 24 h (MVP) e 2 h (fase de automação).
• Disponibilidade: 99% na loja e no checkout; a produção pode degradar para modo manual.
• Segurança: HTTPS, segredos em cofre, chaves por ambiente, autenticação do painel com 2FA, links de entrega assinados e com expiração, princípio do menor privilégio; o acesso remoto de administração (ex.: Tailscale) em rede privada.
• Privacidade: logs sem dados pessoais desnecessários; criptografia em repouso para áudios e briefings; exclusão sob pedido.
• Observabilidade: logs estruturados por pedido, métricas de custo e latência por motor, alertas de fila e de falha.
• Custo: orçamento máximo de motor por pedido e alerta diário; contador de gerações por faixa final.
• Manutenibilidade: adaptadores de motor independentes; prompts versionados; testes automatizados do fluxo.
• Resiliência: reexecução idempotente de etapas; se o motor falhar, o fallback entra; o cliente é avisado de atraso.
• Acessibilidade e idioma: interface em pt-BR; linguagem simples; e-mails e mensagens legíveis no celular.
• Governança de IA: avaliação periódica dos agentes com um conjunto de casos de teste (pedidos normais, casos-limite de compliance, tentativas de manipulação do agente).
9. Dados e integrações
Entidades principais: Cliente, Pedido, Produto, Pagamento, Briefing, Letra (versões), Faixa (candidatas), Motor, Plano/Cota do motor, Aprovação, Entrega, Licença (certificado), Revisão, Reembolso, Avaliação, Cupom, Evento de auditoria.
Integrações:
• Pagamento: Pix e cartão via Mercado Pago, Asaas ou Stripe [DECIDIR].
• Mensageria: WhatsApp Business API e e-mail transacional.
• LLMs dos agentes: Claude e outros, com roteamento por tarefa.
• Motores: Lyria (API), ElevenLabs (conector já existente), ACE-Step via fal.ai, Mureka e Suno em modo assistido.
• Armazenamento de áudio com URL assinada; banco relacional; fila de tarefas.
• Fiscal: emissão de NFS-e ou recibo [VALIDAR].
• Operação interna: ClickUp (tarefas), agenda (prazos), Malfoyd (assistente) e, se for usado, o Router Control com o roteador de modelos (confirmar se «NineHouter» é o 9Router na porta 20128).
10. Operação e métricas
Processo diário: o operador revisa a fila de aprovação, ouve as candidatas, aprova ou pede regeneração, trata exceções e responde reclamações escaladas.
KPIs: pedidos por semana; conversão visita → pedido; tempo médio de entrega; gerações por faixa final; custo de motor por faixa; margem por pedido; taxa de revisão; taxa de reembolso; NPS ou nota média; recorrência e indicações; percentual de pedidos bloqueados por compliance.
Metas iniciais sugeridas: entrega em até 24 h em 90% dos pedidos; nota média ≥ 4,5; revisões ≤ 25%; reembolso ≤ 5%; no máximo 5 gerações por faixa final.
11. Riscos e mitigações
Risco
Impacto
Mitigação
Mudança de termos ou preços de um motor
Alto
Abstração de motor; revisão mensal dos termos; fallback pronto
Qualidade da voz em pt-BR insuficiente
Alto
Teste cego na Fase 0; escolher o motor por resultado, não por fama
Cota da Suno ou do plano esgotada
Médio
Controle de cota, roteamento para pay-per-use
Processo por conteúdo ilícito ou plágio
Alto
Filtros, aprovação humana, termos, registro de provas, jurídico
Ausência de direito autoral na faixa IA
Médio
Não prometer autoria; vender licença de uso; incluir parte humana (letra, edição) quando possível
Cliente insatisfeito e abuso de revisão
Médio
Limites claros, briefing aprovado, política de reembolso
Fraude de pagamento ou chargeback
Médio
Pix, confirmação por webhook, antifraude do gateway
Vazamento de dados pessoais
Alto
Minimização, criptografia, controle de acesso, política LGPD
Agente manipulado (prompt injection) pelo cliente
Médio
Saídas estruturadas, ferramentas com permissão mínima, ações críticas com aprovação humana
Dependência do Hil como único aprovador
Médio
Automatizar por amostragem nas fases seguintes e documentar o processo
Política de WhatsApp para bots
Médio
Canal web como alternativa; checar regras antes de lançar
Custo de prévias que não convertem
Médio
Prévia em motor de custo marginal ~zero, limite por visitante, métrica de custo por lead e de conversão prévia → pedido
Concorrente consolidado com prévia grátis e SEO programático
Alto
Diferir por licença comercial, certificado e aprovação humana; não competir por preço
Prévia canibaliza o produto curto
Médio
Prévia só nos produtos de 2 min, com corte de no máximo 40% da faixa e sem download
Mini vendido abaixo do custo percebido como "trilha de fundo"
Médio
Vender personalização e licença comercial, não trilha genérica; comparar com o substituto gratuito (analiseSWOT.md §3)
Ferramenta de vídeo com cláusula de não revenda
Médio
Pipeline próprio em ffmpeg; quando usar SaaS, ler o ToS e cotar plano customizado
Content ID reivindicando vídeos de clientes
Médio
Não registrar faixas em Content ID e manter lista de vídeos autorizados
Vídeo vendido abaixo do custo de produção
Alto
Automatizar antes de incluir no Presente, ou vender como add-on de R$19–29 (video-com-letra.md)
12. Roadmap
Fase 0 — Validação (≈2 semanas): teste cego dos motores; revisão jurídica inicial; landing page e catálogo; teste do funil dos concorrentes diretos (quiz, prévia, checkout) com dados descartáveis; 10–20 pedidos-piloto vendidos manualmente (Pix manual) para validar preço, prazo e demanda; fechar a escolha do gateway.
Fase 1 — MVP semi-manual (≈4–6 semanas): checkout com Pix, briefing assistido por agente, letrista, prévia cantada com limite de uso, geração em modo assistido ou API (Lyria), painel simples de curadoria, entrega com página e certificado, registro de auditoria, Termo de Uso e Política de Privacidade publicados.
Fase 2 — Automação (≈6–8 semanas): orquestrador completo, roteador de motores, QA automático (transcrição e métricas), WhatsApp integrado, vídeo com letra, cupons e indicações, relatórios.
Fase 3 — Escala: aprovação humana por amostragem, produto Negócio (jingles), assinatura ou combos, parcerias (cerimonialistas, fotógrafos, lojas de presente), API ou revenda, novos idiomas. O concorrente direto já opera assinatura mensal (R$39,90) com álbum privado, então vale testar recorrência antes da Fase 3.
Os prazos são estimativas e dependem da disponibilidade do Hil e dos resultados da Fase 0.
13. Critérios de aceite do MVP
• Pedido pago inicia o fluxo de geração final sem intervenção; pedido não pago não consome geração além da prévia gratuita.
• Prévia de 30 s é liberada sem cartão apenas nos produtos de 2 min, com o nome correto do homenageado, e nunca é confundida com a entrega.
• O Mini entrega sem prévia cantada, e a oferta deixa isso explícito antes do pagamento.
• Custo médio de motor por prévia fica abaixo de R$0,10 e o limite de prévias por visitante bloqueia abuso [VALIDAR com os primeiros 50 leads].
• Briefing completo coletado em até 10 mensagens em 80% dos casos de teste.
• Letra bloqueada nos casos de teste de compliance (política, artista, ódio, trecho de letra conhecida).
• Nenhuma faixa é entregue sem aprovação registrada.
• Cada faixa entregue tem motor, plano, data, ID, prompt e certificado vinculados.
• Todo vídeo entregue registra a licença de cada camada (áudio, fonte, imagem) e tem certificado que cobre o vídeo.
• Cota mensal de cada motor é controlada e bloqueia ao esgotar.
• Link de entrega expira e não é indexável.
• Pedido de exclusão de dados é atendido pelo painel.
• Termo de Uso, Política de Privacidade e modelo de licença revisados por advogado.
• Pelo menos 10 pedidos-piloto entregues dentro do prazo-alvo.
14. Decisões abertas e pendências
1. Escolha do gateway de pagamento e do enquadramento fiscal (MEI, ME, outro) com contador.
2. Motor principal após o teste cego em pt-BR.
3. Confirmar no ToS: uso comercial grátis do Treblo; licença do Google no Producer.ai/Flow Music; duração máxima de Mureka e Suno; existência de API oficial do Mureka.
4. Definir a política de reembolso e o tratamento do direito de arrependimento para produto personalizado.
5. Definir canal principal de atendimento (WhatsApp, site ou ambos) e conferir as regras para bots de IA.
6. Nome da marca, domínio e exemplos de áudio para a landing page.
7. Onde fica o repositório do Router Control e se o NineHouter é o 9Router da porta 20128.
8. Orçamento mensal de motores e teto de custo por pedido.
9. Quem opera quando o Hil estiver indisponível (prazo e plano de contingência).
10. Ambiente de hospedagem: nuvem gerenciada ou Docker próprio (WSL/Tailscale, como no teste do MausBot), considerando disponibilidade e segurança.
11. Limite de prévias grátis por visitante e política antiabuso, com bloqueio por IP e por dia.
12. Posicionamento de preço frente ao piso de R$49,90 do mercado, considerando a licença comercial e o certificado como argumento de valor.
13. Definir se o Mini é produto de entrada ou add-on de um pedido maior, e qual desconto ele sustenta sem canibalizar o Padrão.
14. Definir se o vídeo com letra entra no Presente ou vira add-on de R$19–29, e validar as licenças de revenda das ferramentas de vídeo.
15. Próximos passos imediatos
1. Rodar o teste cego com uma letra-padrão de 1 min.
2. Escrever a primeira versão do Termo de Uso, da Política de Privacidade e do certificado de licença e enviar para revisão jurídica.
3. Criar a landing page com 3 áudios de exemplo e vender os 10 primeiros pedidos manualmente.
4. Definir o schema de briefing e os prompts dos agentes Letrista e Compliance, com 30 casos de teste.
5. Escolher o gateway e abrir o fluxo de Pix com webhook.
6. Testar o funil de Hosanna Song até o checkout, com e-mail descartável, para medir telas do quiz, ponto de captura do contato e se a prévia sai sem cartão.
7. Rodar as prévias de 30 s em ACE-Step ou Lyria e medir custo e taxa de conversão com os primeiros leads, comparando com o Mini sem prévia.