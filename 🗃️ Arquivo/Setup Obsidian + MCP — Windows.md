# Setup Obsidian + MCP + Claude Desktop — Windows

---

## Passo 1 — Instalar o Node.js

1. Acessar **nodejs.org**
2. Baixar a versão **LTS** (recomendada)
3. Instalar normalmente — marcar a opção "Add to PATH" durante a instalação
4. Após instalar, abrir o **Prompt de Comando** e digitar:
   ```
   node -v
   npm -v
   ```
   Se aparecerem os números de versão, está ok ✅

---

## Passo 2 — Instalar o Obsidian

1. Acessar **obsidian.md**
2. Baixar o instalador para Windows
3. Instalar e abrir o Obsidian
4. Criar um novo vault (escolher uma pasta no computador)
5. Montar a estrutura de pastas:
   ```
   📥 Inbox/
   🏢 [Nome do Cliente]/
     📁 Projetos/
     📅 Reuniões/
     ✅ Tarefas/
     👥 Time/
   🏛️ Raro/
   📝 Diário/
   📚 Referências/
   🗃️ Arquivo/
   ```

---

## Passo 3 — Instalar o plugin Local REST API no Obsidian

1. Dentro do Obsidian → **Configurações** (ícone de engrenagem)
2. **Plugins da comunidade → Desativar modo seguro**
3. Clicar em **Procurar** e buscar por: `Local REST API`
4. Instalar e **ativar** o plugin
5. Ir nas configurações do plugin e copiar a **API Key** gerada
6. Guardar essa chave — vai precisar no Passo 5

---

## Passo 4 — Instalar o Claude Desktop

1. Acessar **claude.ai/download**
2. Baixar o instalador para Windows
3. Instalar e fazer login com a conta da Anthropic

---

## Passo 5 — Configurar o MCP no Claude Desktop

1. Abrir o **Explorador de Arquivos** e navegar até:
   ```
   C:\Users\[seu usuario]\AppData\Roaming\Claude\
   ```
   > Dica: na barra de endereço do Explorador, digitar `%APPDATA%\Claude` e pressionar Enter

2. Abrir o arquivo `claude_desktop_config.json` com o Bloco de Notas
   > Se o arquivo não existir, criar um novo com esse nome

3. Colar o seguinte conteúdo:
   ```json
   {
     "mcpServers": {
       "obsidian": {
         "command": "npx",
         "args": [
           "-y",
           "mcp-obsidian"
         ],
         "env": {
           "OBSIDIAN_API_KEY": "COLE_SUA_API_KEY_AQUI",
           "OBSIDIAN_HOST": "http://127.0.0.1:27123"
         }
       }
     }
   }
   ```

4. Substituir `COLE_SUA_API_KEY_AQUI` pela API Key copiada no Passo 3
5. Salvar o arquivo

---

## Passo 6 — Reiniciar tudo

1. Fechar o Obsidian completamente
2. Fechar o Claude Desktop completamente
3. Reabrir o **Obsidian** primeiro
4. Reabrir o **Claude Desktop** depois
5. Iniciar uma nova conversa e pedir: *"Liste os arquivos do meu vault"*
6. Se aparecer a estrutura de pastas, está funcionando ✅

---

## Passo 7 — Criar o CLAUDE.md no vault

1. Na raiz do vault, criar um arquivo chamado `CLAUDE.md`
2. Colar as instruções de comportamento — estrutura de pastas, rotinas, formato das notas
3. Esse arquivo é o que o Claude lê para entender como trabalhar com o vault

---

## Problemas comuns no Windows

**MCP não conecta:**
- Verificar se o Obsidian está aberto e rodando
- Verificar se o plugin Local REST API está ativado
- Reiniciar os dois aplicativos na ordem: Obsidian primeiro, Claude depois

**npx não reconhecido:**
- O Node.js não foi adicionado ao PATH durante a instalação
- Desinstalar e reinstalar o Node.js marcando a opção "Add to PATH"
- Reiniciar o computador após reinstalar

**Porta 27123 em uso:**
- Nas configurações do plugin Local REST API no Obsidian, trocar a porta para 27124
- Atualizar o `claude_desktop_config.json` com a nova porta

**API Key inválida:**
- Abrir as configurações do plugin no Obsidian e copiar a chave novamente
- Colar no arquivo de configuração sem espaços antes ou depois
