<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pet Blog - Landing Page</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/css/bootstrap.min.css" rel="stylesheet">
    <style>
        body {
            background-image: url('https://img.freepik.com/vetores-gratis/fundo-de-impressoes-de-patas-de-design-plano_23-2151169523.jpg');
            background-size: cover;
            background-attachment: fixed;
        }

        .bg-overlay {
            background-color: rgba(255, 255, 255, 0.9);
            padding: 20px;
            border-radius: 10px;
        }

        .pet-icon {
            width: 150px;
            height: 150px;
            object-fit: cover;
            border-radius: 50%;
        }

        .pet-photo {
            width: 100%;
            height: 200px;
            object-fit: cover;
            border-radius: 10px;
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
                        <button class="btn btn-primary me-2" data-bs-toggle="modal" data-bs-target="#loginModal">Entrar</button>
                    </li>
                    <li class="nav-item">
                        <button class="btn btn-outline-primary" data-bs-toggle="modal" data-bs-target="#registerModal">Cadastrar</button>
                    </li>
                </ul>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <header class="bg-primary text-center py-5">
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
            <div class="row">
                <div class="col-md-4 text-center">
                    <img src="https://cisavet.com.br/arquivos/banco-de-imagens/categoria-1/dicas-na-hora-de-escolher-um-cao-como-companheiro-20161125143942.jpg" alt="Ícone Companhia" class="pet-icon mb-3">
                    <h4>Companhia e Amizade</h4>
                    <p>Ter um pet traz muita companhia e amizade para o dia a dia, ajudando a combater a solidão e melhorando o humor.</p>
                </div>
                <div class="col-md-4 text-center">
                    <img src="https://blog-static.petlove.com.br/wp-content/uploads/2021/05/Mulher-gato-no-colo-380x260.jpg" alt="Ícone Redução do Estresse" class="pet-icon mb-3">
                    <h4>Redução do Estresse</h4>
                    <p>Animais ajudam a reduzir o estresse e a ansiedade, criando um ambiente mais calmo e harmonioso.</p>
                </div>
                <div class="col-md-4 text-center">
                    <img src="https://vetery.com.br/wp-content/uploads/2023/03/atividades-fisicas-para-seu-pet.jpg" alt="Ícone Atividades Físicas" class="pet-icon mb-3">
                    <h4>Atividades Físicas</h4>
                    <p>Com um pet, você se mantém mais ativo, seja em caminhadas com cães ou brincadeiras com gatos e outros animais.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Meu Pet Section -->
    <section class="py-5 bg-light">
        <div class="container bg-overlay">
            <h2 class="text-center mb-5">Meu Pet</h2>
            <div class="row mb-4">
                <div class="col-md-12 text-center">
                    <form action="upload.php" method="POST" enctype="multipart/form-data" class="mb-4">
                        <div class="mb-3">
                            <input type="file" name="photo" class="form-control" required>
                        </div>
                        <button type="submit" class="btn btn-primary">Enviar Foto do Meu Pet</button>
                    </form>
                </div>
            </div>
            <div class="row">
                <!-- Fotos Dinâmicas Aqui -->
                <?php
                require 'config.php';
                $stmt = $pdo->query("SELECT * FROM user_photos ORDER BY uploaded_at DESC");
                $photos = $stmt->fetchAll();
                foreach ($photos as $photo):
                ?>
                <div class="col-md-4 mb-4">
                    <div class="card">
                        <img src="<?= htmlspecialchars($photo['photo_path']); ?>" alt="Foto do Pet" class="pet-photo card-img-top">
                        <div class="card-body text-center">
                            <p class="card-text">Foto enviada por: <?= htmlspecialchars($photo['user_id']); ?></p>
                        </div>
                    </div>
                </div>
                <?php endforeach; ?>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-dark text-light text-center py-4">
        <p class="mb-0">© 2024 Pet Blog - Todos os Direitos Reservados.</p>
    </footer>

    <!-- Modais -->
    <!-- Modal de Login -->
    <div class="modal fade" id="loginModal" tabindex="-1" aria-labelledby="loginModalLabel" aria-hidden="true">
        <div class="modal-dialog">
            <div class="modal-content">
                <div class="modal-header">
                    <h5 class="modal-title" id="loginModalLabel">Login</h5>
                    <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
                </div>
                <div class="modal-body">
                    <form id="loginForm">
                        <div class="mb-3">
                            <label for="loginEmail" class="form-label">E-mail</label>
                            <input type="email" class="form-control" id="loginEmail" placeholder="Digite seu e-mail" required>
                        </div>
                        <div class="mb-3">
                            <label for="loginPassword" class="form-label">Senha</label>
                            <input type="password" class="form-control" id="loginPassword" placeholder="Digite sua senha" required>
                        </div>
                        <button type="submit" class="btn btn-primary w-100">Entrar</button>
                    </form>
                </div>
            </div>
        </div>
    </div>

    <!-- Modal de Cadastro -->
    <div class="modal fade" id="registerModal" tabindex="-1" aria-labelledby="registerModalLabel" aria-hidden="true">
        <div class="modal-dialog">
            <div class="modal-content">
                <div class="modal-header">
                    <h5 class="modal-title" id="registerModalLabel">Cadastro</h5>
                    <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
                </div>
                <div class="modal-body">
                    <form id="registerForm">
                        <div class="mb-3">
                            <label for="registerName" class="form-label">Nome Completo</label>
                            <input type="text" class="form-control" id="registerName" placeholder="Digite seu nome completo" required>
                        </div>
                        <div class="mb-3">
                            <label for="registerEmail" class="form-label">E-mail</label>
                            <input type="email" class="form-control" id="registerEmail" placeholder="Digite seu e-mail" required>
                        </div>
                        <div class="mb-3">
                            <label for="registerPassword" class="form-label">Senha</label>
                            <input type="password" class="form-control" id="registerPassword" placeholder="Crie uma senha" required>
                        </div>
                        <button type="submit" class="btn btn-primary w-100">Cadastrar</button>
                    </form>
                </div>
            </div>
        </div>
    </div>

    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/js/bootstrap.bundle.min.js"></script>
</body>
</html>
