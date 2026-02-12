# 📘 Escola de Contas — Guia Completo de Deploy

## 📁 Arquivos do Projeto

| Arquivo | Função |
|---------|--------|
| `escola-de-contas.html` | Landing page de inscrições (arquivo único, pronto pra publicar) |
| `admin-escola-de-contas.html` | Painel admin para editar conteúdo e gerar novas versões |
| `GUIA-GOOGLE-FORMS.md` | Passo a passo da integração com Google Forms |
| `GUIA-COMPLETO.md` | Este guia |

---

## 🚀 Deploy Rápido (5 minutos)

### Opção A — Hospedagem Gratuita (GitHub Pages)

1. Crie uma conta no [GitHub](https://github.com) (se não tiver)
2. Crie um novo repositório: `escola-de-contas`
3. Faça upload do arquivo `escola-de-contas.html` renomeando para `index.html`
4. Vá em **Settings → Pages → Source: main branch**
5. Acesse: `https://seuusuario.github.io/escola-de-contas/`

### Opção B — Netlify (Drag & Drop)

1. Acesse [app.netlify.com/drop](https://app.netlify.com/drop)
2. Arraste a pasta com o `index.html` (renomeie o escola-de-contas.html)
3. Pronto! Gera um link público automaticamente
4. Opcional: configure domínio personalizado

### Opção C — Servidor Próprio / TCM-PA

1. Envie o arquivo `escola-de-contas.html` para o servidor web
2. Acesse via URL do servidor
3. Não precisa de backend, banco de dados, PHP ou Node — é tudo HTML/CSS/JS puro

---

## 📊 Google Forms — Coleta de Dados

### Já Configurado

O site já está integrado com seu Google Forms:
- **Form ID:** `1FAIpQLSfHwVX-53NsItdGpcD-hyh7OVfPJUy3vn6skiPUpdY44pGA2g`
- Os entry IDs de cada campo já estão embutidos no código

### Como Funciona

1. O usuário preenche os dados e seleciona os cursos
2. Ao confirmar, o site envia um POST silencioso para o Google Forms
3. Os dados aparecem na planilha vinculada ao Forms
4. O usuário vê a tela de sucesso com confetti normalmente

### Acessar os Dados

1. Abra seu Google Forms
2. Clique na aba **"Respostas"**
3. Clique no ícone do Google Sheets (quadrado verde)
4. Pronto — planilha com todas as inscrições

### Campos Coletados

| Coluna | Dado |
|--------|------|
| Carimbo | Data/hora automático do Google |
| Nome Completo | Nome do inscrito |
| E-mail | E-mail do inscrito |
| CPF | CPF validado |
| Telefone | Telefone com DDD |
| Município | Um dos 144 municípios do Pará |
| Órgão | Prefeitura, Câmara, Autarquia, etc. |
| Cargo | Cargo/função do servidor |
| Turno 1-5 | Nome do curso + instrutor selecionado |
| Total | Quantidade de cursos escolhidos |

---

## 🛠 Painel Admin

### Como Usar

1. Abra `admin-escola-de-contas.html` no navegador (localmente)
2. Edite o conteúdo nas abas:
   - **🏠 Geral** — título, subtítulo, ano, badge, tags, tema de cores
   - **📅 Turnos & Cursos** — adicionar/remover/editar turnos e cursos
   - **📝 Formulário** — campos pessoais, órgãos, termos
   - **💬 Mensagens** — textos de sucesso e validação
   - **📊 Google Forms** — configurar/atualizar entry IDs
3. Clique **"Gerar Site"** para baixar a nova versão

### Dicas
- O admin salva no localStorage do navegador — seus dados persistem entre sessões
- Use **"Preview"** para visualizar antes de gerar
- Use **"Exportar JSON"** para backup da configuração
- Use **"Resetar"** para voltar à configuração padrão

---

## 📱 Fluxo do Usuário

```
1. 👤 Dados Pessoais → preenche nome, email, CPF, telefone, município, órgão, cargo
2. 📅 Turno 1 (Seg AM) → escolhe um curso ou pula
3. 📅 Turno 2 (Seg PM) → escolhe um curso ou pula
4. 📅 Turno 3 (Ter AM) → escolhe um curso ou pula
5. 📅 Turno 4 (Ter PM) → escolhe um curso ou pula
6. 📅 Turno 5 (Qua AM) → escolhe um curso ou pula
7. ✅ Confirmar → revisa dados + cursos → confirma → 🎉 confetti!
```

### Validações
- CPF: algoritmo completo de validação (dígitos verificadores)
- E-mail: formato válido
- Campos obrigatórios: nome, email, CPF, telefone, município, órgão, cargo
- Mínimo 1 curso selecionado para confirmar
- Máscara automática no CPF e telefone

---

## ⚙️ Especificações Técnicas

- **Zero dependências** — não usa React, Vue, Angular ou frameworks
- **Arquivo único** — todo CSS, JS e HTML num único .html
- **Mobile-first** — responsivo para celular, tablet e desktop
- **Offline-ready** — funciona sem internet (exceto envio ao Google Forms)
- **Google Fonts** — DM Sans + Playfair Display (carrega online)
- **144 municípios** — todos os municípios do Pará embutidos
- **Tamanho:** ~73KB (landing page) | ~130KB (admin)

---

## 🔄 Atualizações Futuras

Para alterar cursos, turnos ou qualquer conteúdo:

1. Abra o `admin-escola-de-contas.html` localmente
2. Faça as alterações desejadas
3. Clique em **"Gerar Site"**
4. Substitua o arquivo no servidor pelo novo gerado
5. Os dados do Google Forms continuam na mesma planilha

---

## 📞 Limites e Observações

- **Google Forms:** máximo ~20.000 envios/dia (gratuito)
- **Sem duplicação:** o Forms não impede envios duplicados (mesmo CPF pode inscrever mais de uma vez)
- **CORS:** o envio usa `mode: no-cors`, então não é possível confirmar se o Google recebeu (mas funciona)
- **Backup local:** cada inscrição também é salva no localStorage do navegador do usuário
