# Awesome Termux

Personalização do Termux sem root: cores, fundos sólidos, fontes e configurações do Zsh/Powerlevel10k.

> Projeto inicial. Teste em uma instalação do Termux atualizada. Faça backup antes de aplicar mudanças.

## Recursos

- Menu interativo em português.
- Presets de cores, incluindo AMOLED, roxo escuro e verde Android.
- Cor personalizada por código hexadecimal (`#RRGGBB`).
- Instalação de fonte `.ttf` por URL ou arquivo local.
- Backup automático de `~/.termux`.
- Restauração do backup mais recente.
- Não instala Zsh/Oh My Zsh/Powerlevel10k automaticamente nesta versão.

## Instalação

No Termux:

```bash
pkg update -y
pkg install git -y
git clone https://github.com/SEU-USUARIO/Awesome-Termux.git
cd Awesome-Termux
chmod +x install.sh
./install.sh
```

Ou baixe o ZIP do repositório, extraia e execute `./install.sh`.

## Menu

O script permite:
1. Aplicar presets de cores.
2. Definir cores personalizadas de fundo, texto e cursor.
3. Instalar uma fonte `.ttf` a partir de uma URL.
4. Instalar uma fonte `.ttf` já presente no armazenamento.
5. Restaurar o backup mais recente.

### Fontes

O Termux usa `~/.termux/font.ttf` para a fonte personalizada. O script preserva a fonte anterior no backup antes de substituí-la.

Exemplo de fonte JetBrains Mono Regular:

```text
https://raw.githubusercontent.com/JetBrains/JetBrainsMono/master/fonts/ttf/JetBrainsMono-Regular.ttf
```

Para fontes com ícones, use uma Nerd Font compatível. A fonte regular JetBrains Mono não contém todos os glifos Nerd Font.

### Tamanho da fonte

Ajuste o tamanho no próprio Termux usando o gesto de pinça na tela. O tamanho visual pode variar conforme a densidade da tela e a versão do aplicativo.

## Arquivos do Termux

- `~/.termux/colors.properties`: paleta de cores.
- `~/.termux/font.ttf`: fonte personalizada.
- `termux-reload-settings`: recarrega as configurações.

## Presets incluídos

| Nome | Fundo | Texto | Cursor |
|---|---|---|---|
| AMOLED | `#000000` | `#E6E6E6` | `#FFFFFF` |
| Purple Dark | `#0F0B12` | `#E6E1E9` | `#BB86FC` |
| Android Green | `#07140B` | `#E8F5E9` | `#00C853` |
| Dracula | `#282A36` | `#F8F8F2` | `#BD93F9` |
| Nord | `#2E3440` | `#D8DEE9` | `#88C0D0` |

## Segurança

- Leia os scripts antes de executá-los.
- Use fontes de sites/repositórios confiáveis.
- Não execute scripts remotos com `curl | bash`.
- O projeto não precisa de root.
- Este projeto não altera permissões Android nem configurações de rede.

## Estado do projeto

- [x] Menu de personalização básico
- [x] Presets de cores
- [x] Cor hexadecimal personalizada
- [x] Instalação de fonte por URL ou arquivo local
- [x] Backup e restauração
- [ ] Integração opcional com Zsh e Powerlevel10k
- [ ] Mais presets e fontes

## Licença

MIT. Veja `LICENSE`.
