# Cabecalho.PHP
Criação do cabeçalho.php com CSS

<?php
// Exibe o CSS no topo da página
?>
<style>
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }

    body {
        font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        background-color: #f2f2f2;
        color: #333;
        padding: 20px;
    }

    div {
        background-color: #ffffff;
        padding: 30px;
        margin: 0 auto;
        max-width: 700px;
        border-radius: 10px;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        text-align: center;
    }

    h1 {
        color:rgb(70, 26, 105);
        font-size: 2rem;
    }

    a {
        color: #0077cc;
        text-decoration: none;
        transition: color 0.3s;
    }

    a:hover {
        color: #005fa3;
    }

    button {
        background-color: #0077cc;
        color: white;
        border: none;
        padding: 10px 20px;
        margin: 5px;
        border-radius: 5px;
        cursor: pointer;
        font-size: 1rem;
        transition: background-color 0.3s;
    }

    button:hover {
        background-color: #005fa3;
    }

    p {
        font-size: 1.1rem;
        margin-top: 20px;
    }

    h3 {
        display: inline-block;
        margin-left: 10px;
        font-size: 1rem;
        color: #cc0000;
        cursor: pointer;
    }

    h3:hover {
        color: #990000;
    }
</style>
<?php

if (!isset($_SESSION['nivel'])) {
    // usuário não logado
    ?>
  <div>
        <a href="index.php"><h1>Minhas Aventuras</h1></a>
        <br>
        <p>
            Faça seu <a href="login.php">Login</a>
            ou crie a sua <a href="#">Conta</a>
        </p>
    </div>
    <?php
} else if ($_SESSION['nivel'] == 1) {
    ?>
    <div>
        <a href="index.php"><h1>Minhas Aventuras</h1></a>
        <br>
        <p>
            <?= $_SESSION['apelido'] ?> Bem vindo ao meu negócio!
            <a href="logout.php"><h3>Sair</h3></a>
        </p>
    </div>
    <?php
} else if ($_SESSION['nivel'] == 10) {
    ?>
    <div>
        <a href="index.php"><h1>Minhas Aventuras</h1></a>
        <br>
        <a href="cadastrausuario.php"><button>Cadastrar Usuário</button></a>
        <a href="listausuario.php"><button>Listar Usuários</button></a>
        <a href="cadastraproduto.php"><button>Cadastrar Produto</button></a>
        <a href="listaproduto.php"><button>Listar Produtos</button></a>
        <p><?= $_SESSION['apelido'] ?> Bem vindo ao meu negócio!
            <a href="logout.php"><h3>Sair</h3></a>
        </p>
    </div>
    <?php
}
?>
