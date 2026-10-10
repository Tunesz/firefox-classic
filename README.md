# Firefox Retrô (visual Firefox 5/6, 2011)

Um tema feito só com CSS que deixa o Firefox atual parecido com o Firefox das versões 4 a 28: botão laranja "Firefox" no topo, abas retas com cantos suaves, barra de navegação clara, botão de voltar redondo e uma nova aba cinza clara com a logo clássica.

> **Este projeto foi desenvolvido com o auxílio e o uso de inteligênc artificial (Claude, da Anthropic).**
> Leia a seção [Limitações e avisos](#limitações-e-avisos) antes de usar.

Autor: João Tunes

<img width="1920" height="1037" alt="Screenshot" src="https://github.com/user-attachments/assets/1d973299-717a-4252-97fb-e6285e02dd00" />

---

## O que tem aqui

| Arquivo | O que faz |
|---|---|
| `userChrome.css` | Muda o visual do navegador: abas, barra de endereço, botão laranja, botão de voltar |
| `userContent.css` | Muda a página de nova aba: fundo cinza claro, logo antiga, caixa de busca retangular |

Os dois são opcionais e independentes. Dá pra usar só o `userChrome.css` e ficar com a nova aba padrão.

## Requisitos

- Firefox em computador (Windows, Linux ou macOS). Foi feito e pensado para o **Firefox 157.0.1 (64 bits) no Windows 10**.
- Não funciona no Firefox de celular.

## Instalação

**1. Ative o suporte a estilos personalizados**
- Digite `about:config` na barra de endereço e aceite o aviso.
- Procure `toolkit.legacyUserProfileCustomizations.stylesheets` e deixe como `true`.

**2. Abra a pasta do seu perfil**
- Digite `about:support` na barra de endereço.
- Ao lado de "Pasta de perfil", clique em **Abrir pasta**.

**3. Crie a pasta `chrome`**
- Dentro da pasta de perfil, crie uma pasta chamada exatamente `chrome` (minúsculo).

**4. Copie os arquivos**
- Coloque `userChrome.css` e `userContent.css` dentro da pasta `chrome`.
- Os nomes precisam estar exatos, com o C maiúsculo. No Windows, ative em Explorador de Arquivos → Exibir → "Extensões de nome de arquivo" para ter certeza de que não ficou `.css.txt`.

**5. Reinicie**
- Em `about:support`, clique em **Limpar cache de inicialização...**. O Firefox reinicia sozinho.
- Abra uma nova aba para ver a página inicial nova.

**6. Posicione o botão laranja**
- Clique com o botão direito numa área vazia da barra de abas → **Personalizar barra de ferramentas**.
- Arraste o botão de menu (os três tracinhos) para o começo da barra de abas, à esquerda das abas. O CSS transforma ele no botão "Firefox".
- Deixe "Barra de título" desmarcada e clique em Concluído.

## Dica opcional: sites também em tema claro

Se o seu Windows está no modo escuro, muitos sites e a nova aba ficam escuros. Para forçar o claro:

- Em `about:config`, procure `layout.css.prefers-color-scheme.content-override` e coloque `1`.

## Se algo não funcionar

| Problema | O que tentar |
|---|---|
| Nada mudou | Confirme o `true` no `about:config`, o nome da pasta `chrome` e dos arquivos, e faça de novo "Limpar cache de inicialização" |
| O topo mudou mas a nova aba não | Confira se o `userContent.css` está na mesma pasta `chrome` do `userChrome.css` |
| O botão laranja não abre o menu | Use a versão mais recente do `userChrome.css` (a regra do ícone dentro do botão precisa estar como invisível, não escondida) |
| O visual ficou torto em algum lugar | Veja a seção abaixo sobre pedir ajustes à IA |
| Depois de atualizar o Firefox quebrou | Normal: os nomes internos dos elementos mudam entre versões. Peça um ajuste à IA com a nova versão |

## Como desfazer

É 100% reversível e não mexe nos seus dados:

1. Apague (ou renomeie) a pasta `chrome` do perfil, ou só os dois arquivos `.css`.
2. Reinicie o Firefox.

Se quiser, volte `toolkit.legacyUserProfileCustomizations.stylesheets` para `false`. Para desfazer a dica do tema claro, clique em "Redefinir" ao lado de `layout.css.prefers-color-scheme.content-override` no `about:config`.


## Limitações e avisos

- **Desenvolvido com auxílio de IA e não testado em todas as versões.** Os seletores de CSS usados dependem de como o Firefox 157 organiza a interface por dentro. Em outras versões, partes podem não funcionar.
- **Status dos testes:** a barra superior (abas, barra de endereço, botão laranja) foi conferida por captura de tela. A nova aba (`userContent.css`) e o menu do botão laranja ainda são experimentais.
- **É só visual.** O botão laranja é o botão de menu do Firefox com outra aparência e o menu que abre é o atual, não o antigo.
- **Windows 10/11:** os botões de minimizar, maximizar e fechar são do sistema e não mudam. O efeito de vidro transparente do Aero não existe mais, então ele foi imitado com degradês cinza.
- **Faixa de ícones da página inicial antiga** (Downloads, Bookmarks, History, Add-ons, Sync, Settings) não foi recriada, porque o Firefox bloqueia links para páginas internas a partir de páginas comuns.
- **Leia antes de usar.** Arquivos CSS só alteram aparência, não executam programas, mas vale dar uma olhada no conteúdo de qualquer arquivo antes de instalar, inclusive este.
- Os arquivos usam `!important` em vários lugares, de propósito, para vencer os estilos padrão do Firefox.

## Créditos e marcas

- Desenvolvido com o auxílio e o uso de  (Claude, da Anthropic).
- "Firefox" e o logotipo do Firefox são marcas da Mozilla. Este é um projeto de fã, **sem qualquer vínculo com a Mozilla**. A logo antiga é usada apenas como referênc visual e fica embutida no `userContent.css`.
- Inspiração visual: Firefox 4 a 28 (2011 a 2014).

## Licença

Distribuído sob a licença [MIT](LICENSE). A licença cobre o código deste projeto e não inclui a logo e a marca do Firefox, que pertencem à Mozilla.
