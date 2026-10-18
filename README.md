# MYNSTR

## O que é

O sistema é uma loja online de músicas curtas (1–2 min), personalizadas, com letra e voz em português do Brasil. A entrega é no mesmo dia, e não em dias. Agentes de IA cuidam do atendimento, da letra, da geração, da curadoria e da entrega. Nas fases iniciais, uma pessoa ouve e aprova cada faixa antes de ela sair.

A proposta ao cliente: contar a história em poucos minutos e receber a música pronta, com licença de uso clara. A letra é aprovada antes de qualquer geração de música.

## Para quem

Três públicos iniciais, ainda como hipótese:

- Presentes e datas (aniversário, casamento, formatura, Dia das Mães, declarações). É a hipótese principal.
- Pequenos negócios (jingle simples, vinheta para redes sociais).
- Criadores de conteúdo (trilha com voz para vídeos).



## Jornada

1. Descoberta pela landing page, Instagram, WhatsApp ou indicação.
2. Pedido: produto, nome, ocasião, e-mail e WhatsApp, com aceite do Termo de Uso e da Política de Privacidade.
3. Pagamento: Pix primeiro, cartão como segunda opção. A produção só começa depois da confirmação.
4. Briefing por conversa (WhatsApp ou site): ocasião, pessoas, memórias, estilo, voz e o que evitar.
5. Letra proposta ao cliente, que aprova ou pede ajuste dentro do limite do produto.
6. Geração de candidatas, curadoria e escolha da melhor.
7. Aprovação interna: uma pessoa ouve a faixa antes da entrega.
8. Entrega por link privado, com player, download, certificado de licença e, quando contratado, capa ou vídeo.
9. Pós-venda: revisão, avaliação e indicação.

Estados do pedido: rascunho, aguardando pagamento, pago, briefing, letra proposta, letra aprovada, gerando, curadoria, aprovação interna, entregue, em revisão e concluído. Desvios: bloqueado por compliance, cancelado e reembolsado.

## O que o cliente recebe

Preços e limites abaixo são hipóteses, a validar com pedidos reais. O prazo-alvo no MVP é de 24 horas.


| Produto  | Conteúdo                                                  | Preço sugerido | Revisões |
| -------- | --------------------------------------------------------- | -------------- | -------- |
| Mini     | até 1 min, letra curta, 1 estilo                          | R$20–29        | 1        |
| Padrão   | até 2 min, letra completa, capa simples                   | R$39           | 2        |
| Presente | Padrão + vídeo com letra e dedicatória                    | R$49–59        | 2        |
| Negócio  | Padrão + versão instrumental + licença comercial ampliada | R$79–149       | 2        |


A licença oferecida é de uso perpétuo e não exclusivo, com certificado em PDF e rastreio de cada faixa. O sistema não promete exclusividade nem direito autoral sobre a parte gerada por IA.

## Como funciona

Um orquestrador determinístico (máquina de estados) chama agentes especializados, com entrada e saída estruturadas. Os agentes não decidem sozinhos sobre pagamento, reembolso, entrega final ou conteúdo sensível. Essas decisões passam por regra fixa ou por uma pessoa.

- **Atendimento:** conversa, tira dúvidas e monta o briefing.
- **Compliance:** analisa briefing e letra e pode aprovar, pedir ajuste ou bloquear.
- **Letrista:** escreve a letra em português do Brasil, com estrutura e métrica para a duração.
- **Diretor musical:** define estilo, andamento, voz e o motor a usar.
- **Gerador:** produz as candidatas e registra motor, plano, data, identificador e prompt.
- **Curadoria:** ranqueia as candidatas e confere duração, áudio, pronúncia e aderência à letra.
- **Entrega:** monta a página, o certificado e o aviso ao cliente, só depois da aprovação humana.
- **Pós-venda:** trata revisão, avaliação e reativação, dentro do limite do produto.

Vários motores ficam atrás de uma interface única. O roteamento considera custo, qualidade e cota. Motor sem API oficial opera em modo assistido: o agente prepara prompt e letra, uma pessoa gera no site do fornecedor e devolve o arquivo para o sistema registrar. APIs não oficiais ficam de fora.

## Fora de escopo por ora

- Exclusividade de obra.
- Registro de direito autoral de faixa 100% gerada por IA.
- Clonagem de voz de pessoa real.
- Cover ou reprodução de música existente.
- Venda para cinema, TV, rádio ou games de estúdio.
- Distribuição em streaming em nome do cliente.



## Estado atual

O sistema está na fase de documentação e validação (Fase 0). Este repositório ainda não tem aplicação, instalação nem comando para rodar. O próximo passo é o teste cego dos motores, a revisão jurídica inicial e os primeiros pedidos-piloto vendidos de forma manual.

## Documentos

- [requisitos.md](requisitos.md) — visão, jornada, agentes, requisitos, motores, compliance, operação e roadmap (v2.0).
- [analiseSWOT.md](analiseSWOT.md) — forças, fraquezas, oportunidades, ameaças e concorrentes.
- [suno-loja-micro-musicas.md](suno-loja-micro-musicas.md) — resumo de direitos, riscos de mau uso e mapa de plataformas de música com IA.



## Pendências

Marca, domínio, gateway de pagamento, enquadramento fiscal, motor principal, canal de atendimento e as demais decisões em aberto estão na seção 14 de [requisitos.md](requisitos.md).

## Aviso

Este material não é parecer jurídico nem contábil. Itens que dependem de advogado, contador ou dos termos vigentes dos fornecedores estão marcados nos documentos de origem.