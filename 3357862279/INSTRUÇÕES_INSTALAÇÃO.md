# 🎮 Instruções de Instalação - Tradução PT-BR do Immortal Way of Life

## ⚠️ PROBLEMA COMUM: Tradução não funciona

Se a tradução não está funcionando, siga estas etapas:

## 📋 Pré-requisitos

1. **BepInEx 5.x** instalado no jogo
2. Jogo **Immortal Way of Life** original instalado

## 🔧 Instalação Correta

### Passo 1: Instalar o BepInEx no Jogo

1. Baixe o **BepInEx 5.x (x64)** de: https://github.com/BepInEx/BepInEx/releases
2. Extraia o conteúdo do BepInEx **diretamente na pasta do jogo**
3. Execute o jogo **uma vez** para o BepInEx criar a estrutura de pastas
4. Feche o jogo

### Passo 2: Instalar os Arquivos de Tradução

Copie os arquivos deste MOD para a pasta do jogo:

```
[Pasta do Jogo]/
├── BepInEx/
│   ├── config/
│   │   ├── AutoTranslatorConfig.ini          ← Copie daqui: config/
│   │   ├── BepInEx.cfg
│   │   └── com.sinai.unityexplorer.cfg
│   │
│   ├── core/                                  ← Copie daqui: core/
│   │   ├── 0Harmony.dll
│   │   ├── BepInEx.Harmony.dll
│   │   └── [outros arquivos .dll]
│   │
│   ├── plugins/                               ← Copie daqui: plugins/
│   │   ├── EngTranslatorMod.dll
│   │   ├── XUnity.AutoTranslator/
│   │   ├── XUnity.ResourceRedirector/
│   │   └── Translations/
│   │
│   └── Translation/                           ← Copie daqui: Translation/
│       └── pt/
│           ├── Text/
│           │   ├── MyShit.txt
│           │   ├── extra.txt
│           │   ├── XUnityManualSubst.txt
│           │   └── [outros arquivos]
│           └── Texture/
```

### Passo 3: Verificar a Instalação

1. Vá para a pasta: `[Jogo]/BepInEx/`
2. Execute o jogo
3. Feche o jogo
4. Verifique se foi criado um arquivo de log em: `BepInEx/LogOutput.log`
5. Abra o arquivo de log e procure por:
   - `[Info   :   BepInEx] BepInEx X.X.X.X` ← BepInEx carregou
   - `[Info   : XUnity.AutoTranslator]` ← Plugin de tradução carregou
   - `[Info   : EngTranslatorMod]` ← Mod de tradução carregou

## 🐛 Problemas Comuns

### Tradução não aparece no jogo

**Causa 1: Endpoint do tradutor não configurado**
- Edite: `BepInEx/config/AutoTranslatorConfig.ini`
- Linha 2: `Endpoint=` está vazio
- **Solução**: Como você já tem traduções prontas, isso não deve ser problema, mas se quiser tradutor automático online, configure:
  ```ini
  Endpoint=GoogleTranslateV2
  ```

**Causa 2: BepInEx não está carregando**
- Verifique se existe `winhttp.dll` na pasta raiz do jogo
- Se não existir, reinstale o BepInEx

**Causa 3: Arquivos no lugar errado**
- Os arquivos devem estar em `[Pasta do Jogo]/BepInEx/`, não no repositório GitHub

**Causa 4: Modo Silent ativado**
- No `AutoTranslatorConfig.ini`, linha 53: `EnableSilentMode=True`
- Isso faz o plugin não mostrar erros. Mude para `False` temporariamente para debug.

### Como verificar o caminho correto do jogo

**Steam:**
1. Clique com botão direito no jogo → Propriedades
2. Arquivos Locais → Procurar arquivos locais
3. Esta é a pasta onde você deve instalar o BepInEx

**Exemplo de caminho:**
```
C:\Program Files (x86)\Steam\steamapps\common\Immortal Way of Life\
```

## 📝 Testando a Tradução

1. Inicie o jogo
2. Pressione **F10** para abrir o console de debug (se habilitado)
3. Pressione **Alt + 0** para recarregar traduções (atalho padrão do XUnity)
4. Verifique se o texto em chinês está traduzido para português

## 🔍 Debug Avançado

Se ainda não funcionar, habilite o console para ver erros:

1. Edite: `BepInEx/config/BepInEx.cfg`
2. Procure por `[Logging.Console]`
3. Mude: `Enabled = true`
4. Execute o jogo - uma janela de console aparecerá mostrando logs em tempo real

## 📞 Suporte

Se após seguir todos os passos ainda não funcionar:
1. Verifique o arquivo `BepInEx/LogOutput.log`
2. Procure por linhas com `[Error]` ou `[Warning]`
3. Compartilhe essas linhas para diagnóstico

---

## ✅ Checklist de Instalação

- [ ] BepInEx instalado na pasta do jogo
- [ ] Jogo executado uma vez após instalar BepInEx
- [ ] Pasta `BepInEx` criada automaticamente
- [ ] Arquivos de tradução copiados para `BepInEx/Translation/pt/`
- [ ] Plugins copiados para `BepInEx/plugins/`
- [ ] Config copiado para `BepInEx/config/`
- [ ] Arquivo `LogOutput.log` foi criado após executar o jogo
- [ ] Log mostra que XUnity.AutoTranslator foi carregado
