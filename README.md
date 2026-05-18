# Projeto-FullStack
Neste projeto foi desenvolvido o jogo Tower Knight, um jogo de plataforma onde o jogador controla um cavaleiro que deve subir uma torre pulando de plataforma em plataforma, utilizando HTML, CSS e JavaScript para a construção da interface, estilização e implementação de toda a lógica da aplicação. Além disso, o Node.js juntamente com o Express foram utilizados para realizar o gerenciamento do servidor e das rotas responsáveis pelo carregamento das páginas do sistema. O jogo é executado diretamente no navegador por meio do elemento canvas, permitindo a renderização dinâmica de todos os componentes gráficos, como o cavaleiro, as plataformas normais, móveis e frágeis. O jogador controla a movimentação do cavaleiro utilizando as teclas direcionais do teclado, devendo pular de plataforma em plataforma para subir o mais alto possível.
Todo o funcionamento da aplicação ocorre através da manipulação do DOM, responsável pela interação entre o JavaScript e os elementos HTML da página. Além disso, o jogo utiliza atualização contínua através de um loop principal com requestAnimationFrame, garantindo movimentação fluida, verificação de colisões, atualização do placar e renderização em tempo real dos elementos presentes no canvas.

SERVIDOR
O arquivo server.js é responsável por toda a configuração e inicialização do servidor da aplicação Tower Knight. Ele foi desenvolvido utilizando o ambiente de execução Node.js juntamente com o Express, que facilita a criação de servidores web e o gerenciamento de rotas de forma simples e organizada. Sua principal função é permitir que o navegador consiga acessar corretamente todas as páginas, arquivos CSS e JavaScript do projeto.
Para isso, o servidor configura uma pasta pública chamada public, responsável por armazenar os arquivos estáticos da aplicação, como estilos e o código JavaScript do jogo. Além disso, o arquivo define as rotas principais do sistema, determinando qual página HTML será exibida quando o usuário acessar determinados endereços no navegador. Por exemplo, ao acessar a rota (/), o servidor carrega a página inicial do projeto; já nas rotas (/jogo) e (/dev), são carregadas respectivamente a tela do jogo e a página do desenvolvedor.

PÁGINAS HTML
Todos os HTMLs possuem a importação do CSS e seguem o mesmo estilo visual medieval do projeto:(<link rel="stylesheet" href="/style.css">)

Comeco.html :funciona como a página inicial do projeto Tower Knight. Ela apresenta o jogo ao usuário antes da partida começar, exibindo o título, a descrição do jogo, os controles do teclado e o botão para iniciar.

jogo.html : é a página principal do projeto, pois é nela que o jogo realmente funciona. Essa página contém o canvas do jogo, o placar de altura atual, o recorde e a importação do JavaScript. O canvas é a área onde todos os elementos do jogo são desenhados usando JavaScript. Dentro dele aparecem o cavaleiro e as plataformas.

dev's.html: funciona como uma página de apresentação do desenvolvedor do projeto, contendo nome, RA e curso.

CSS
O arquivo style.css é responsável por toda a aparência visual do projeto Tower Knight. Ele organiza os elementos da interface e aplica o tema medieval ao site, utilizando cores douradas, fontes temáticas e efeitos de brilho.

JavaScript (principal.js)
O arquivo principal.js é a principal parte do projeto Tower Knight, pois ele controla toda a lógica e funcionamento do jogo. É através dele que acontecem a movimentação do cavaleiro, o sistema de câmera, as colisões, os três tipos de plataforma e a atualização da tela em tempo real.

Tipos de plataforma: o jogo possui três tipos gerados aleatoriamente:
Normal (60% de chance) — plataforma fixa dourada
Móvel (25% de chance) — se move para os lados
Frágil (15% de chance) — some após ser pisada

Sistema de câmera: quando o cavaleiro chega no terço superior da tela, a câmera sobe empurrando tudo para baixo, mantendo o jogo sempre visível.
function loop() {
    moverCav();
    verificarColisao();
    atualizarPlats();
    atualizarCamera();
    desenhar();
    requestAnimationFrame(loop);
}
O requestAnimationFrame faz o loop rodar cerca de 60 vezes por segundo, garantindo animação fluida.

Bloqueio da rolagem:
if (['ArrowLeft','ArrowRight','ArrowUp','ArrowDown',' '].includes(e.key)) e.preventDefault();
Impede que as setas do teclado rolem a página do navegador durante o jogo.

Conclusão
O desenvolvimento do Tower Knight permitiu aplicar diversos conceitos importantes da programação web de forma prática. Durante o projeto foram utilizados HTML para estruturar as páginas, CSS para estilização da interface medieval e JavaScript para toda a lógica do jogo, incluindo movimentação, colisões, câmera, plataformas e atualização em tempo real do canvas. Além do funcionamento do jogo, o projeto também trabalhou conceitos como manipulação do DOM, objetos, eventos de teclado, funções, estruturas de repetição e controle de animações com requestAnimationFrame. A separação dos arquivos em páginas e funções específicas ajudou na organização do código e facilitou a manutenção da aplicação. O resultado final foi um jogo funcional, interativo e totalmente executado no navegador, demonstrando como tecnologias web podem ser utilizadas no desenvolvimento de aplicações dinâmicas e jogos 2D.
