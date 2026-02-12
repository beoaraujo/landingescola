# 📊 Integração Google Forms — Guia Rápido

## ✅ Status: JÁ CONFIGURADO

Seu Google Forms já está integrado no site com os seguintes IDs:

```
Form ID: 1FAIpQLSfHwVX-53NsItdGpcD-hyh7OVfPJUy3vn6skiPUpdY44pGA2g

entry.137986107  → Nome Completo
entry.387358485  → E-mail
entry.170998325  → CPF
entry.1003090881 → Telefone
entry.1275313173 → Município
entry.1044411995 → Órgão
entry.2131353385 → Cargo/Função
entry.2119241331 → Turno 1 (Seg Manhã)
entry.1270592413 → Turno 2 (Seg Tarde)
entry.632286599   → Turno 3 (Ter Manhã)
entry.1768044873 → Turno 4 (Ter Tarde)
entry.1531634535 → Turno 5 (Qua Manhã)
entry.419920169  → Total de Cursos
```

---

## 📋 Acessar as Respostas

1. Abra o Google Forms
2. Clique na aba **"Respostas"** (no topo)
3. Clique no **ícone verde do Sheets** (canto superior direito)
4. Pronto — todas as inscrições estarão na planilha

---

## 🧪 Testar

1. Abra o `escola-de-contas.html` **localmente no navegador** (fora do Claude)
2. Preencha uma inscrição com dados fictícios
3. Confirme a inscrição
4. Verifique se a linha apareceu na planilha do Google Sheets

> ⚠️ O teste NÃO funciona dentro do Claude.ai (o iframe bloqueia requisições externas).
> Baixe o arquivo e abra no navegador.

---

## 🔄 Se Precisar Recriar o Forms

Caso crie um novo Google Forms:

1. Crie **13 perguntas** (todas "Resposta curta"):
   - Nome Completo, E-mail, CPF, Telefone, Município, Órgão, Cargo
   - Turno 1, Turno 2, Turno 3, Turno 4, Turno 5, Total de Cursos

2. Clique em **⋮ → Preencher formulário automaticamente**

3. Preencha cada campo com o marcador:
   - Nome → `CAMPO_NOME`
   - E-mail → `CAMPO_EMAIL`
   - CPF → `CAMPO_CPF`
   - Telefone → `CAMPO_TEL`
   - Município → `CAMPO_MUN`
   - Órgão → `CAMPO_ORGAO`
   - Cargo → `CAMPO_CARGO`
   - Turno 1 → `CAMPO_T1` ... Turno 5 → `CAMPO_T5`
   - Total → `CAMPO_TOTAL`

4. Clique **"Gerar link"** e copie

5. No **admin-escola-de-contas.html**, aba 📊 Google Forms:
   - Cole o link no campo "link pré-preenchido"
   - Clique **"Extrair IDs automaticamente"**
   - Gere o site novamente
