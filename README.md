# Kinvia — site de pré-lançamento

Landing page da Kinvia (app brasileiro de rotina do bebê), em fase de lista de espera.

- **`index.html`** — página principal (funil de lista de espera + planos + IA + contato)
- **`historia.html`** — a história da Kinvia
- **`privacidade.html`** — política de privacidade (LGPD)
- **`telas/ emo/ photos/ videos/`** — imagens e vídeo usados na página

Site estático, sem build. Fontes vêm do Google Fonts; o resto é local.

## Backend (Supabase)

Os formulários gravam no projeto Supabase **Olivia** via API REST (chave pública, RLS só de inserção):
- Lista de espera → tabela `kv_waitlist`
- Contato → tabela `kv_contato`

Os leads/mensagens são vistos no painel do Supabase (Table Editor).

## Como publicar (GitHub → Netlify)

1. Crie um repositório vazio no GitHub (ex.: `kinvia-site`).
2. No seu terminal, dentro desta pasta:
   ```bash
   git remote add origin https://github.com/SEU_USUARIO/kinvia-site.git
   git push -u origin main
   ```
3. Em [app.netlify.com](https://app.netlify.com) → **Add new site → Import an existing project → GitHub** → escolha o repositório.
4. Sem comando de build. Publish directory = `.` (já definido no `netlify.toml`). Clique em **Deploy**.
5. O site sobe em um endereço `*.netlify.app` (dá pra trocar o nome e ligar o domínio `kinvia.app` depois).

A cada `git push`, o Netlify republica sozinho.
