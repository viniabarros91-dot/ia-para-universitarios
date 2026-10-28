# Orçamento Pronto: gerador de orçamento grátis + lista de espera da versão PRO

Página única (`index.html`) que serve para duas coisas:

1. **Ferramenta grátis e útil de verdade.** O prestador de serviço monta o orçamento, baixa em PDF e envia pelo WhatsApp. Tudo roda no navegador, sem servidor e sem cadastro. Os dados do profissional ficam salvos no aparelho.
2. **Validação da versão PRO com IA.** Quem usa a ferramenta vê a oferta (orçamento por áudio, tabela de preços, histórico, follow-up) e pode entrar na lista de espera.

O nome "Orçamento Pronto" é provisório. Antes de registrar domínio, confira se ele está livre (registro.br e INPI) e troque no `<title>`, no topo, no rodapé e na folha do orçamento.

---

## 1. Publicar (grátis, ~10 minutos)

A lista de espera usa o **Netlify Forms**, que recebe os cadastros sem precisar de servidor. O plano grátis aceita 100 envios por mês.

1. Crie uma conta em netlify.com.
2. **Opção A (mais simples):** em *Add new site → Deploy manually*, arraste a pasta `orcamento/`.
   **Opção B:** em *Add new site → Import from Git*, escolha este repositório e defina *Base directory* = `orcamento`. Cada novo commit publica sozinho.
3. Em *Site configuration → Forms*, ative a detecção de formulários e publique de novo.
4. Os cadastros aparecem em *Forms → lista-espera*. Em *Form notifications* dá para receber um e-mail a cada cadastro.
5. Opcional: compre um domínio `.com.br` (~R$ 40/ano) e conecte em *Domain management*.

> Aberta direto do computador (sem o Netlify), a ferramenta funciona, mas o formulário da lista de espera mostra erro, porque é o Netlify que recebe os envios.

## 2. Validar antes de construir a versão PRO

**Como divulgar sem aparecer**
- Grupos de Facebook e WhatsApp de eletricistas, pintores, marceneiros e afins: "fiz uma ferramenta grátis de orçamento em PDF, quem quiser testar…".
- Anúncio no Meta com R$ 100–200 para profissionais de construção e reformas, com um vídeo de tela mostrando o orçamento sendo montado.
- Páginas de SEO/GEO depois, como "modelo de orçamento de pintura", "como fazer orçamento de elétrica", cada uma levando à ferramenta.

**Meça**
- Visitantes (ative o *Netlify Analytics* ou instale Plausible / Google Analytics).
- Cadastros na lista de espera e a resposta "quantos orçamentos você faz por mês".

**Critério de decisão sugerido** (ajuste à sua realidade)
- **≥ 50 cadastros em 2–3 semanas**, ou **≥ 5% dos visitantes se cadastrando**: siga para a versão PRO.
- Entre 20 e 50: converse por WhatsApp com 5–10 inscritos para entender o que eles mais querem e ajuste a oferta.
- Menos de 20 com tráfego razoável (500+ visitas): troque a promessa ou o nicho antes de investir em programação.

Bônus: quem faz **16+ orçamentos por mês** é o melhor cliente para a versão paga. Fale com essas pessoas primeiro.

## 3. Próximo passo: a versão PRO

Com a validação feita, o app PRO usa:
- **Supabase** para login, clientes, tabela de preços e histórico;
- **API do Claude (Haiku)** para transformar texto ou áudio transcrito em itens do orçamento, com resposta em formato fixo (JSON);
- **Mercado Pago ou Stripe** para a assinatura mensal;
- esta mesma página como porta de entrada (a ferramenta grátis continua atraindo usuários).

Custo estimado por orçamento gerado com IA: menos de R$ 0,01.
