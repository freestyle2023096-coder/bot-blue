<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BLUE ALUGUEL | Loja de Bots WhatsApp</title>
    <style>
        /* ESTILOS BÁSICOS */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: Arial, sans-serif;
            background: #000814;
            color: white;
            line-height: 1.6;
        }
        
        /* HEADER */
        header {
            background: linear-gradient(135deg, #0052FF 0%, #0038a8 100%);
            padding: 20px;
            text-align: center;
            box-shadow: 0 2px 10px rgba(0,0,0,0.3);
        }
        
        .logo {
            font-size: 24px;
            font-weight: bold;
            margin-bottom: 10px;
        }
        
        nav {
            margin-top: 10px;
        }
        
        nav button {
            background: white;
            color: #0052FF;
            border: none;
            padding: 10px 20px;
            margin: 0 5px;
            border-radius: 20px;
            font-weight: bold;
            cursor: pointer;
        }
        
        /* CONTEÚDO PRINCIPAL */
        main {
            padding: 20px;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        /* PLANOS */
        .planos {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin: 40px 0;
        }
        
        .plano {
            background: #001d3d;
            border: 2px solid #0052FF;
            border-radius: 10px;
            padding: 25px;
            text-align: center;
            transition: transform 0.3s;
        }
        
        .plano:hover {
            transform: translateY(-5px);
        }
        
        .plano-popular {
            border-color: #ffd700;
            background: #001d3d;
        }
        
        .preco {
            font-size: 32px;
            font-weight: bold;
            color: #0052FF;
            margin: 15px 0;
        }
        
        .btn {
            display: block;
            width: 100%;
            background: #0052FF;
            color: white;
            text-align: center;
            padding: 15px;
            border-radius: 8px;
            text-decoration: none;
            font-weight: bold;
            margin-top: 20px;
            border: none;
            cursor: pointer;
        }
        
        /* CHAT */
        .chat {
            background: #001d3d;
            border-radius: 10px;
            padding: 20px;
            margin: 40px 0;
            display: none;
        }
        
        .chat-mensagens {
            height: 300px;
            overflow-y: auto;
            border: 1px solid #0052FF;
            border-radius: 5px;
            padding: 15px;
            margin-bottom: 20px;
        }
        
        .mensagem {
            background: #003566;
            padding: 10px;
            border-radius: 5px;
            margin-bottom: 10px;
        }
        
        .mensagem-bot {
            border-left: 4px solid #0052FF;
        }
        
        .mensagem-cliente {
            border-left: 4px solid #00b4d8;
            text-align: right;
        }
        
        /* PIX */
        .pix-box {
            background: #004d00;
            border: 2px solid #00ff00;
            border-radius: 10px;
            padding: 20px;
            margin: 20px 0;
        }
        
        .chave-pix {
            font-family: monospace;
            background: black;
            padding: 15px;
            border-radius: 5px;
            margin: 15px 0;
            word-break: break-all;
        }
        
        /* ADMIN */
        .admin {
            background: #1a1a2e;
            border-radius: 10px;
            padding: 25px;
            margin: 40px 0;
            display: none;
        }
        
        input {
            width: 100%;
            padding: 12px;
            margin: 10px 0;
            border-radius: 5px;
            border: 1px solid #0052FF;
            background: #000814;
            color: white;
        }
        
        /* FOOTER */
        footer {
            text-align: center;
            padding: 30px 20px;
            background: #001d3d;
            margin-top: 50px;
        }
        
        .whatsapp-btn {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: #25D366;
            color: white;
            width: 60px;
            height: 60px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 30px;
            text-decoration: none;
            box-shadow: 0 4px 15px rgba(37, 211, 102, 0.4);
        }
        
        /* RESPONSIVO */
        @media (max-width: 768px) {
            .planos {
                grid-template-columns: 1fr;
            }
            
            nav button {
                padding: 8px 15px;
                font-size: 14px;
            }
        }
    </style>
</head>
<body>
    <!-- HEADER -->
    <header>
        <div class="logo">🤖 BLUE ALUGUEL</div>
        <p>Aluguel profissional de bots para WhatsApp</p>
        <nav>
            <button onclick="mostrarHome()">HOME</button>
            <button onclick="mostrarChat()">CHAT</button>
            <button onclick="mostrarAdmin()">ADMIN</button>
        </nav>
    </header>

    <!-- HOME -->
    <main id="home">
        <h2 style="text-align: center; margin: 30px 0;">ESCOLHA SEU PLANO</h2>
        
        <div class="planos">
            <!-- PLANO 1 -->
            <div class="plano">
                <h3>TESTE GRÁTIS</h3>
                <div class="preco">R$ 0,00</div>
                <p>7 dias de teste grátis</p>
                <button class="btn" onclick="selecionarPlano(1)">SELECIONAR</button>
            </div>
            
            <!-- PLANO 2 -->
            <div class="plano">
                <h3>MENSAL BLUE</h3>
                <div class="preco">R$ 69,90</div>
                <p>30 dias de acesso</p>
                <button class="btn" onclick="selecionarPlano(2)">SELECIONAR</button>
            </div>
            
            <!-- PLANO 3 -->
            <div class="plano plano-popular">
                <h3>TRIMESTRAL PRO</h3>
                <div class="preco">R$ 189,90</div>
                <p>90 dias de acesso</p>
                <button class="btn" onclick="selecionarPlano(3)">SELECIONAR</button>
            </div>
            
            <!-- PLANO 4 -->
            <div class="plano">
                <h3>ANUAL ELITE</h3>
                <div class="preco">R$ 690,00</div>
                <p>365 dias de acesso</p>
                <button class="btn" onclick="selecionarPlano(4)">SELECIONAR</button>
            </div>
        </div>
    </main>

    <!-- CHAT -->
    <main id="chat" class="chat">
        <h2>💬 CHAT DE VENDAS</h2>
        <div class="chat-mensagens" id="chatMensagens">
            <div class="mensagem mensagem-bot">
                Olá! Sou o BLUE Bot. Escolha um plano para começar!
            </div>
        </div>
        
        <div style="display: flex; gap: 10px;">
            <input type="text" id="mensagemInput" placeholder="Digite sua mensagem..." style="flex: 1;">
            <button class="btn" onclick="enviarMensagem()" style="width: auto;">Enviar</button>
        </div>
        
        <div id="pixSection" style="display: none;">
            <div class="pix-box">
                <h3>💰 PAGAMENTO VIA PIX</h3>
                <p>Chave Pix:</p>
                <div class="chave-pix" id="chavePix">bqoqb2nroqo1hq9sao</div>
                <button class="btn" onclick="copiarPix()" style="background: #00ff00; color: black;">
                    📋 COPIAR CHAVE PIX
                </button>
                <p style="margin-top: 15px; font-size: 14px;">
                    Envie o comprovante para:<br>
                    WhatsApp: 55 99 98117-5724
                </p>
            </div>
        </div>
        
        <button class="btn" onclick="mostrarHome()" style="margin-top: 20px; background: #666;">
            VOLTAR PARA PLANOS
        </button>
    </main>

    <!-- ADMIN -->
    <main id="admin" class="admin">
        <h2>⚙️ PAINEL ADMINISTRATIVO</h2>
        
        <div style="background: #000814; padding: 20px; border-radius: 10px; margin: 20px 0;">
            <h3>Login ADM</h3>
            <input type="password" id="senhaAdmin" placeholder="Digite a senha ADM">
            <button class="btn" onclick="loginAdmin()">ENTRAR</button>
        </div>
        
        <div id="painelConfig" style="display: none;">
            <h3>Configurações</h3>
            
            <label>Nome do Dono:</label>
            <input type="text" id="nomeDono" value="Pedro Bots">
            
            <label>WhatsApp:</label>
            <input type="text" id="whatsappDono" value="5599981175724">
            
            <label>Chave Pix Atual:</label>
            <input type="text" id="pixAtual" value="bqoqb2nroqo1hq9sao">
            
            <label>Nova Chave Pix:</label>
            <input type="text" id="novaPix" placeholder="Cole sua nova chave Pix">
            
            <button class="btn" onclick="atualizarPix()" style="background: #00ff00; color: black;">
                ATUALIZAR CHAVE PIX
            </button>
            
            <button class="btn" onclick="mostrarHome()" style="margin-top: 20px;">
                VOLTAR PARA LOJA
            </button>
        </div>
    </main>

    <!-- FOOTER -->
    <footer>
        <p>BLUE ALUGUEL &copy; 2024</p>
        <p>WhatsApp: 55 99 98117-5724</p>
        <p>Sistema de aluguel de bots para WhatsApp</p>
    </footer>

    <!-- BOTÃO WHATSAPP -->
    <a href="https://wa.me/5599981175724" target="_blank" class="whatsapp-btn">
        💬
    </a>

    <!-- JAVASCRIPT SIMPLES -->
    <script>
        // DADOS
        let planos = [
            { id: 1, nome: "TESTE GRÁTIS", preco: 0, dias: 7 },
            { id: 2, nome: "MENSAL BLUE", preco: 69.90, dias: 30 },
            { id: 3, nome: "TRIMESTRAL PRO", preco: 189.90, dias: 90 },
            { id: 4, nome: "ANUAL ELITE", preco: 690.00, dias: 365 }
        ];
        
        let passoChat = 0;
        let planoSelecionado = null;
        
        // MOSTRAR SESSÕES
        function mostrarHome() {
            document.getElementById('home').style.display = 'block';
            document.getElementById('chat').style.display = 'none';
            document.getElementById('admin').style.display = 'none';
        }
        
        function mostrarChat() {
            document.getElementById('home').style.display = 'none';
            document.getElementById('chat').style.display = 'block';
            document.getElementById('admin').style.display = 'none';
        }
        
        function mostrarAdmin() {
            document.getElementById('home').style.display = 'none';
            document.getElementById('chat').style.display = 'none';
            document.getElementById('admin').style.display = 'block';
        }
        
        // SELECIONAR PLANO
        function selecionarPlano(id) {
            let plano = planos.find(p => p.id === id);
            planoSelecionado = plano;
            passoChat = 1;
            
            mostrarChat();
            
            // Limpar chat
            document.getElementById('chatMensagens').innerHTML = '';
            
            // Adicionar mensagem do bot
            adicionarMensagemBot(`🎉 Você selecionou o plano ${plano.nome}!<br>💵 R$ ${plano.preco.toFixed(2)}<br>📅 ${plano.dias} dias<br><br>📝 <b>Digite seu NOME COMPLETO:</b>`);
        }
        
        // ENVIAR MENSAGEM NO CHAT
        function enviarMensagem() {
            let input = document.getElementById('mensagemInput');
            let texto = input.value.trim();
            
            if (!texto) return;
            
            // Adicionar mensagem do cliente
            adicionarMensagemCliente(texto);
            input.value = '';
            
            // Processar resposta
            setTimeout(function() {
                processarRespostaChat(texto);
            }, 500);
        }
        
        function processarRespostaChat(texto) {
            if (passoChat === 1) {
                // Passo 1: Pegar nome
                passoChat = 2;
                adicionarMensagemBot(`👤 Nome: ${texto}<br><br>📱 Agora digite seu WHATSAPP com DDD:<br>(Ex: 5599981175724)`);
            }
            else if (passoChat === 2) {
                // Passo 2: Pegar WhatsApp
                passoChat = 3;
                adicionarMensagemBot(`✅ Tudo certo! Agora vou gerar seu pedido...`);
                
                // Mostrar chave Pix após 1 segundo
                setTimeout(function() {
                    document.getElementById('pixSection').style.display = 'block';
                    adicionarMensagemBot(`💰 <b>PAGAMENTO VIA PIX</b><br><br>Copie a chave Pix abaixo e envie o comprovante no WhatsApp.`);
                }, 1000);
            }
        }
        
        function adicionarMensagemBot(texto) {
            let chat = document.getElementById('chatMensagens');
            let div = document.createElement('div');
            div.className = 'mensagem mensagem-bot';
            div.innerHTML = texto;
            chat.appendChild(div);
            chat.scrollTop = chat.scrollHeight;
        }
        
        function adicionarMensagemCliente(texto) {
            let chat = document.getElementById('chatMensagens');
            let div = document.createElement('div');
            div.className = 'mensagem mensagem-cliente';
            div.innerHTML = texto;
            chat.appendChild(div);
            chat.scrollTop = chat.scrollHeight;
        }
        
        // COPIAR PIX
        function copiarPix() {
            let chave = document.getElementById('chavePix').textContent;
            navigator.clipboard.writeText(chave);
            alert('✅ Chave Pix copiada! Envie o comprovante no WhatsApp.');
            
            setTimeout(function() {
                window.open('https://wa.me/5599981175724?text=Olá!%20Acabei%20de%20fazer%20o%20pagamento%20do%20plano%20' + encodeURIComponent(planoSelecionado.nome) + '.%20Aqui%20está%20o%20comprovante.', '_blank');
            }, 500);
        }
        
        // ADMIN
        function loginAdmin() {
            let senha = document.getElementById('senhaAdmin').value;
            
            if (senha === '0000' || senha === 'admin') {
                document.getElementById('painelConfig').style.display = 'block';
                alert('✅ Acesso concedido!');
            } else {
                alert('❌ Senha incorreta!');
            }
        }
        
        function atualizarPix() {
            let novaChave = document.getElementById('novaPix').value.trim();
            
            if (!novaChave) {
                alert('Digite uma nova chave Pix!');
                return;
            }
            
            document.getElementById('chavePix').textContent = novaChave;
            document.getElementById('pixAtual').value = novaChave;
            document.getElementById('novaPix').value = '';
            
            alert('✅ Chave Pix atualizada com sucesso!');
        }
        
        // INICIAR MOSTRANDO HOME
        mostrarHome();
    </script>
</body>
</html>
