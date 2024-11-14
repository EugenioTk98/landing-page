<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pet Blog - Landing Page</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/css/bootstrap.min.css" rel="stylesheet">
    <style>
        /* Fundo da página com tema de pets */
        body {
            background-image: url('https://img.freepik.com/vetores-gratis/fundo-de-impressoes-de-patas-de-design-plano_23-2151169523.jpg?t=st=1731541613~exp=1731545213~hmac=afb69b62900ce208e75f6e2866f0b891a7b371c513888a6f7b83370672139532&w=1380');
            background-size: cover;
            background-attachment: fixed;
        }

        /* Estilização para melhorar a legibilidade */
        .bg-overlay {
            background-color: rgba(255, 255, 255, 0.9);
            padding: 20px;
            border-radius: 10px;
        }

        /* Ajuste dos ícones de imagem */
        .pet-icon {
            width: 80px;
            height: 80px;
            border-radius: 50%;
        }
    </style>
</head>
<body>

    <!-- Navbar -->
    <nav class="navbar navbar-expand-lg navbar-light bg-light bg-overlay">
        <div class="container">
            <a class="navbar-brand" href="#">Pet Blog</a>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarNav">
                <ul class="navbar-nav ms-auto">
                    <li class="nav-item">
                        <a class="btn btn-primary me-2" href="#">Entrar</a>
                    </li>
                    <li class="nav-item">
                        <a class="btn btn-outline-primary" href="#">Cadastrar</a>
                    </li>
                </ul>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <header class="bg-primary text-white text-center py-5">
        <div class="container bg-overlay">
            <h1>Bem-vindo ao Pet Blog</h1>
            <p class="lead">Um espaço para compartilhar e aprender sobre o convívio com nossos amigos peludos</p>
            <a href="#" class="btn btn-light btn-lg mt-3">Conheça o Blog</a>
        </div>
    </header>

    <!-- Sobre Pets Section -->
    <section class="py-5">
        <div class="container bg-overlay">
            <h2 class="text-center mb-5">A Importância do Convívio com Animais de Estimação</h2>
            <style>
                /* Ajuste dos ícones de imagem */
                .pet-icon {
                    width: 150px; /* Define a largura desejada */
                    height: 150px; /* Define a altura desejada */
                    object-fit: cover; /* Ajusta a imagem dentro do contêiner sem distorção */
                    border-radius: 50%; /* Forma circular */
                }
            </style>
            
            <div class="row">
                <div class="col-md-4 text-center">
                    <img src="https://cisavet.com.br/arquivos/banco-de-imagens/categoria-1/dicas-na-hora-de-escolher-um-cao-como-companheiro-20161125143942.jpg" alt="Ícone Companhia" class="pet-icon mb-3">
                    <h4>Companhia e Amizade</h4>
                    <p>Ter um pet traz muita companhia e amizade para o dia a dia, ajudando a combater a solidão e melhorando o humor.</p>
                </div>
                <style>
                    /* Ajuste dos ícones de imagem */
                    .pet-icon {
                        width: 150px; /* Define a largura desejada */
                        height: 150px; /* Define a altura desejada */
                        object-fit: cover; /* Ajusta a imagem dentro do contêiner sem distorção */
                        border-radius: 50%; /* Forma circular */
                    }
                </style>
                
                <div class="col-md-4 text-center">
                    <img src="https://blog-static.petlove.com.br/wp-content/uploads/2021/05/Mulher-gato-no-colo-380x260.jpg" alt="Ícone Redução do Estresse" class="pet-icon mb-3">
                    <h4>Redução do Estresse</h4>
                    <p>Animais ajudam a reduzir o estresse e a ansiedade, criando um ambiente mais calmo e harmonioso.</p>
                </div>
                <div class="col-md-4 text-center">
                    <img src="https://cdn.pixabay.com/photo/2018/03/26/14/43/dog-3263346_960_720.jpg" alt="Ícone Atividades Físicas" class="pet-icon mb-3">
                    <h4>Atividades Físicas</h4>
                    <p>Com um pet, você se mantém mais ativo, seja em caminhadas com cães ou brincadeiras com gatos e outros animais.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-light text-center py-4 bg-overlay">
        <div class="container">
            <p>&copy; 2024 Pet Blog. Todos os direitos reservados.</p>
            <p>
                <a href="#" class="text-primary me-3">Política de Privacidade</a>
                <a href="#" class="text-primary">Termos de Serviço</a>
            </p>
        </div>
    </footer>

    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/js/bootstrap.bundle.min.js"></script>
</body>
</html>
