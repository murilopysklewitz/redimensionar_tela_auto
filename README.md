🖥️ Script de Reposicionamento Automático do Opera GX
📋 Descrição

Este script monitora continuamente a posição e o tamanho da janela do Opera GX e garante que ela permaneça totalmente visível e centralizada na segunda tela.
Ele é especialmente útil em setups com duais monitores, onde a abertura de jogos em tela cheia na tela principal pode deslocar ou desalinhar janelas na segunda tela.

⚙️ Funcionalidades

Detecta automaticamente todos os monitores conectados.

Identifica a segunda tela e define suas dimensões e posição.

Localiza a janela do Opera GX aberta.

Move e redimensiona a janela para preencher 100% da segunda tela.

Força o modo tela cheia (F11) do navegador.

Monitora em tempo real e corrige automaticamente qualquer deslocamento.

Pode ser convertido em .exe e executado em segundo plano.

🧩 Requisitos

Python 3.9+

Bibliotecas:

pip install pygetwindow keyboard screeninfo

🗂️ Estrutura do Projeto
📁 redimensionar_tela_auto/
 ├── redimensiona.py          # Script principal
 ├── README.md                # (opcional) Documentação do projeto
 ├── /dist                    # Pasta onde o .exe é gerado
 └── /build                   # Arquivos temporários do PyInstaller

🚀 Como Executar o Script
🔹 Opção 1: Rodar direto no Python

Abra o terminal do Anaconda Prompt e execute:

conda activate redimensiona_tela_auto_env
cd "C:\Programação\projeto html, css javascript\redimensionar_tela_auto"
python redimensiona.py


O script iniciará um monitoramento contínuo, verificando a posição do Opera GX a cada 2 segundos.

🧱 Geração do Executável (.exe)

Para criar um executável autônomo (sem depender do Python instalado):

No terminal (Anaconda Prompt):

python -m PyInstaller --onefile --noconsole redimensiona.py


O .exe será gerado na pasta:

dist/redimensiona.exe


Execute o arquivo normalmente para manter o Opera GX fixo na segunda tela.

🪄 Execução Automática no Windows

Para que o script rode automaticamente sempre que o Windows iniciar:

Pressione Win + R e digite:

shell:startup


Copie o arquivo redimensiona.exe para essa pasta.

Reinicie o computador.
O script será iniciado automaticamente em segundo plano.

🔍 Detalhes Técnicos

Biblioteca screeninfo → obtém informações sobre cada monitor (posição e resolução).

Biblioteca pygetwindow → localiza e manipula janelas abertas.

Biblioteca keyboard → envia o atalho F11 para forçar o modo tela cheia.

O loop principal verifica a janela a cada 2 segundos.
Se detectar que ela saiu da posição ou foi redimensionada, a janela é reajustada imediatamente.

⚠️ Limitações e Observações

O script só funciona se o Opera GX já estiver aberto.

Se a janela tiver outro título que não contenha "Opera GX", pode não ser detectada.

O atalho F11 pode piscar a tela se o navegador já estiver em modo tela cheia.

Caso queira apenas maximizar (sem F11), basta remover a linha:

keyboard.press_and_release("f11")

🧠 Ideias de Melhoria

Adicionar suporte para detectar mais de duas telas e escolher qual usar.

Criar um ícone na bandeja do sistema com pausa/retomada do monitoramento.

Registrar logs em arquivo (.log) para diagnóstico de erros.

Interface simples (GUI) para escolher o monitor e o intervalo de checagem.

🪪 Autor

Murilo Fuzikawa
🧠 Projeto criado para manter o Opera GX fixo na segunda tela durante jogos em tela cheia.
💻 Ambiente: Python + Anaconda + VS Code
