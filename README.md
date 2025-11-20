# dao

1. Visão geral

Nome da DAO: LiquiWave DAO
Produto central: LiquiWave — um Automated Market Maker (AMM) descentralizado com foco em UX para tokens emergentes, baixos slippage em pares principais, mecanismos de incentivos para provedores de liquidez (LPs) e governança on-chain para parametrizar taxas, incentivos e alocação de tesouraria.
Slogan: “Liquidity, governed by you.”

2. Missão e valores

Missão: Democratizar o acesso à liquidez para projetos emergentes, protegendo usuários através de governança transparente, incentivos alinhados e auditoria contínua de segurança.
Valores: descentralização real, transparência, segurança primeiro, incentivos alinhados, interoperabilidade.

3. Proposta de valor (o que entregamos)

Um DEX (AMM) com interface simples e integração a wallets — foco em experiência do usuário.

Incentivos para LPs (farming, ve-token model, veNFT ou staking).

Governança on-chain para modificar taxas, emissores de incentivos, parceiras e sub-DAO.

Tesouraria que financia grants, auditorias, integração crosschain e marketing.

Ferramentas para projetos listarem pares com proteção (vetting, oracles, whitelisting).

4. Público-alvo

Desenvolvedores de tokens ERC-20/compatible.

Traders on-chain (swappers) e arbitradores.

Provedores de liquidez institucionais/retail.

Teses de investimento e incubadoras de projetos.

5. Tokenomics (modelo sugerido)

Token de governança: LQW (ERC-20)

Fornecimento total: 1.000.000.000 LQW (ajustável em proposta)

Distribuição inicial (exemplo):

20% Liquidity mining / incentivos iniciais (vesting curado por propostas).

20% Tesouraria (para grants, parcerias, aquisições, auditorias).

20% Equipe & Fundadores (vesting 4 anos, 1 ano cliff).

15% Investidores iniciais / advisors (vesting 1–2 anos).

15% Airdrop / Comunidade (retro a usuários de DEXs, LPs).

10% Reserva para parcerias / ecossistema.

Mecanismos adicionais:

veLQW (vote-escrowed): usuários travam LQW por tempo (ex.: 1 semana–4 anos) e recebem veLQW que confere poder de voto e parte das taxas (modelo semelhante ao “ve” usado por alguns DEXs).

Fee switch opcional: parte das taxas do protocolo podem ser redirecionadas para tesouraria e convertidas em LQW para compra e queima ou recompensas — sujeito a votação.

Emissão inicial decrescente: emissão de novos LQW para liquidity mining decai ao longo do tempo.

6. Governança — princípios e mecânica

Princípios: on-chain, transparente, quorum razoável, proteção contra governança hostil.
Componentes:

Snapshot + execução on-chain (Timelock / Governor): Propostas são criadas on-chain; votação com veLQW; se aprovadas, enfileiradas em um timelock (ex.: 48–72h) para execução automática.

Tipos de proposta:

Parâmetros do AMM (taxa de swap base, taxa LP, fee switch).

Emissões / programas de incentivo (pools a serem subsidiados).

Gastos da tesouraria (grants, auditoria, marketing).

Atualizações de contratos (somente via multisig + timelock e após auditoria).

Listagem de novos pares com whitelist.

Requisitos de votação:

Proposer threshold: mínimo de X LQW (ou veLQW) para criar proposta, ou via sinal off-chain por comunidade.

Quorum: percentagem do supply total locked (eg. 2–5% veLQW) para aprovar.

Majoridade: >50% dos votos participativos. Para mudanças críticas (upgrade de core), exigir 2/3 e período de votação maior.

Delegation: voto delegável (para DAOs e indivíduos).

Guardrails de segurança:

Delay (timelock): window para reaver ou coordenar resposta em caso de votação maliciosa.

Emergency multisig: um multisig de 5-7 assinaturas para pausas de emergência (não para tomar decisões permanentes), acionável por votação off-chain e conselheiros de segurança; uso limitado e transparente.

On-chain veto opcional: mecanismo muito custoso para veto — usar apenas como último recurso e deixar claro nas regras.

7. Arquitetura técnica (alto nível)

Contratos principais:

Factory: cria pares.

Pool / Pair: AMM (versão pode ser constante product x*y=k; depois avançar para concentrated liquidity se for estratégico).

Router: rota swaps, suporta multi-hop, limites de slippage, deadline.

LP Token (ERC-20): representando posição de LP (se concentrated, usar NFTs ou positions).

Treasury / Vault: gerencia fundos protocol fee; multisig + timelock.

Governance (Governor + Timelock): execução de propostas.

Incentive contracts: farming, ve-lock, reward distributor.

Oracles / Price feeds: Chainlink ou alternativa para proteções (ex.: price oracles para prevenir manipulação).
Boas práticas:

Modularidade (separar lógica de contabilidade e lógica de swaps).

Upgradeability controlado (proxy pattern só com clear governance path e auditorias).

Extensive unit & integration tests + fuzzing + audits públicos.
Integrações desejadas:

Wallets (MetaMask, Wallet Connect), analytics (The Graph), bridges para cross-chain.

8. Segurança

Auditoria tripla: 2 firmas independentes + bounty público.

Bug bounty / HackerOne / Immunefi.

Testnets and staged mainnet launch: deploy em testnet e mainnet beta com limites de emissão/taxas.

Rate limits e proteção contra flash loans: oracles e checks em pools sensíveis.

Open source: código auditável publicamente.

9. Roadmap (MVP → Year 1)

Fase 0 — Preparação (0–2 meses):

Documento técnico (whitepaper-lite) + tokenomics final.

Time core, advisors, cronograma de auditoria.

Repositório público com roadmap.
Fase 1 — MVP (2–4 meses):

Deploy dos contratos básicos (Factory, Router, Pair).

UI web simples para swap / add liquidity.

Testes e auditorias iniciais.

Pequeno programa de incentivos para bootstrapping de LPs.
Fase 2 — DAO launch (4–6 meses):

Lançamento LQW + veLQW mechanics.

Snapshot / Governor + Timelock deploy.

Airdrop/retro para early users.
Fase 3 — Crescimento (6–12 meses):

Ferramentas de analytics, integração The Graph.

Programas de grants e parcerias.

Suporte a concentrated liquidity / posições customizadas (se viável).
Fase 4 — Maturidade (12+ meses):

Cross-chain bridges, sub-DAOs (grants, security, growth).

Evolução por propostas da comunidade.

10. Plano de comunidade e marketing (teórico)

Canais: Discord (servidor organizado por canais: governance, dev, security, grants), Telegram/Matrix, Twitter/X, Medium/Blog, YouTube para tutoriais.
Estrutura do Discord (teórico):

Canais: anúncios, propostas, discussões técnicas, suporte, validators/infra, bounty.

Roles: contributors, voters (quem stakou), moderators, auditors.
Iniciativas de engajamento:

Airdrop para LPs e usuários de DEXs (snapshot criterioso).

Programa de grants para devs: financiar integrações e infra.

Hackathons + bounty para features e auditorias.

Educação: guias sobre como fornecer liquidez com gestão de risco.
KPIs iniciais:

TVL (Total Value Locked), volume diário, número de usuários ativos, número de propostas criadas, tempo médio para execução de proposições.

11. Operação da tesouraria

Estrutura: multisig + timelock + transparência via explorer de tesouraria.

Uso: pagar auditorias, grants, marketing, operações.

Política financeira: somente despesas aprovadas pela DAO; pequenas despesas operacionais até X dólares podem ser executadas por multisig sem votação, conforme regras definidas.

12. Modelo de listagem e proteção de pares

Vetting opcional: para pares com tokens novos, sugerir auditoria mínima do token ou whitelist por proposta da comunidade (evita scams).

Oracle + delay: para pares sensíveis, adicionar oracle de preço para detectar manipulação antes de permitir grandes swaps.

Slippage warning UI: alertas na interface para tokens com baixo liquidity depth.

13. Riscos principais e mitigação

Governança maliciosa: mitigação com timelock, quorum elevado para mudanças críticas e multisig de emergência.

Exploração de contrato (flash loan): usar oracles e limites; auditorias + bug bounties.

Concentração de tokens (whales): distribuir token com ve-model e vesting para reduzir liquidez inicial centralizada.

Risco legal: consultar advogados locais (especialmente em BR) sobre classificações de tokens, compliance AML/KYC se houver interface fiat ou CEX partnerships.

14. Entregáveis do projeto (o que você vai receber ao final)

Documento de projeto (este doc expandido) com: visão, tokenomics, governança, arquitetura, roadmap.

Especificação técnica de contratos (lista de funções públicas, eventos, invariantes importantes).

Modelo de governança (parâmetros iniciais sugeridos: quorum, proposer threshold, delays, tipos de propostas).

Plano de lançamento (checklist passo-a-passo: testnet → auditorias → mainnet → airdrop → DAO activation).

Plano de comunidade e marketing (scripts de campanha, estrutura de Discord, ideias de airdrop/grants).

Matriz de riscos e plano de mitigação.

Templates: proposta de governance (ex.: formato das propostas padrão), rascunho de multisig rules, termo de vesting para equipe.

15. Exemplo prático — parâmetros iniciais sugeridos

Proposer threshold: 1000 LQW (ou votação por assinatura de 5 membros initial).

Voting period: 3 dias (72h).

Timelock delay: 48 horas para proposições simples, 7 dias para upgrades críticos.

Quorum: 3% do supply total veLQW.

Fee: 0.25% por swap (protocol fee switch 10% das fees para tesouraria, 90% para LPs inicialmente).

Emissão inicial de liquidity mining: 20% do supply alocado a um programa decrescente de 2 anos.

16. Checklist de lançamento (prático)

Auditoria de contratos (mín. 2 firmas).

Testes completos e coverage > 90%.

Deploy em testnet + audit fix + deploy em mainnet.

Setup da multisig da tesouraria + timelock.

Deploy do Governor + Snapshot off-chain infra.

Website e docs (how to provide liquidity, how to vote).

Programa de incentivos e airdrop definido.

Campanha de marketing pré-lançamento + Discord aberto.

17. Métricas de sucesso (6 meses)

TVL alvo inicial: definido com base no mercado (ex.: metas de 1–10M USD primeiro 3 meses).

Volume diário médios e spread médio.

Número de holders LQW que lockaram (veLQW).

Número de propostas válidas e executadas.
