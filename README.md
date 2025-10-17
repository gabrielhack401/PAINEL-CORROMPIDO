# PAINEL-CORROMPIDO
# COLE NO CONSOLE DEVELOPER DO GOOGLE!
// SCRIPT DE SIMULAÇÃO VISUAL DE HACKING - MÁXIMO DE ABAS FAKE
// Totalmente visual, local e seguro.

(function() {
    // VARIÁVEL PARA O DATA URI DA IMAGEM: 
    const MATRIX_IMAGE_DATA_URI = 'COLE_AQUI_SEU_DATA_URI_DA_IMAGEM_MATRIX'; 

    // --- 0. Funções de Limpeza e Estilo Básico ---
    const elementIds = [
        'safe-meme-box', 'matrix-overlay', 'fake-console-window', 'log-window-2', 
        'threat-window', 'data-decoder', 'packet-monitor', 'firewall-status', 
        'security-alerts', 'scanlines-overlay', 'glitch-border', 'safe-meme-style'
    ];

    const cleanUp = () => {
        elementIds.forEach(id => {
            const el = document.getElementById(id);
            if (el) el.remove();
        });
        document.adoptedStyleSheets = document.adoptedStyleSheets.filter(s => s && !s.rules[0]?.cssText.includes('@keyframes safeShake'));
        
        const body = document.body;
        if (body.hasAttribute('data-original-style')) {
            body.style.cssText = body.getAttribute('data-original-style');
            body.removeAttribute('data-original-style');
        } else {
            body.style.background = '';
            body.style.filter = '';
        }
    };
    cleanUp();

    // --- 1. Definição da Animação e Estilos Complexos ---
    const styleSheet = new CSSStyleSheet();
    const complexStyles = `
    @keyframes safeShake {
        0%, 100% { transform: translate(1px, 1px) rotate(0deg); } 10% { transform: translate(-1px, -2px) rotate(-1deg); } 90% { transform: translate(1px, 2px) rotate(0deg); }
    }
    @keyframes blink { 0%, 100% { opacity: 1; } 50% { opacity: 0.5; } }
    @keyframes glitch { 0% { transform: translate(0); } 20% { transform: translate(-2px, 2px); } 40% { transform: translate(-4px, -4px); } 60% { transform: translate(4px, 4px); } 80% { transform: translate(2px, -2px); } 100% { transform: translate(0); } }
    .matrix-text-style {
        font-family: 'Consolas', monospace;
        color: #0F0;
        background: rgba(0, 0, 0, 0.95);
        padding: 5px;
        animation: blink 0.3s infinite step-end;
        font-size: 14px;
        border: 2px solid #0F0;
        box-shadow: 0 0 18px rgba(0, 255, 0, 1);
        z-index: 999998;
        text-shadow: 0 0 5px #0F0;
    }
    #scanlines-overlay {
        position: fixed; top: 0; left: 0; width: 100%; height: 100%; z-index: 999999;
        pointer-events: none;
        background: repeating-linear-gradient(to bottom, rgba(0, 0, 0, 0.2) 0px, rgba(0, 0, 0, 0.3) 1px, transparent 2px, transparent 3px);
        opacity: 0.7;
    }
    #glitch-border {
        position: fixed; top: 0; left: 0; width: 100%; height: 100%; z-index: 999990;
        pointer-events: none;
        box-shadow: 0 0 0 5px red, 0 0 0 10px blue, 0 0 0 15px yellow;
        animation: glitch 0.1s infinite alternate;
        opacity: 0.7;
    }`;

    try {
        // Injeta as regras de estilo de forma segura (Trusted Types Proof)
        complexStyles.match(/@keyframes [^{]+\{[^}]+\}/g).forEach((rule, i) => styleSheet.insertRule(rule, i));
        complexStyles.match(/(\.[a-z\-]+|\#[a-z\-]+) [^{]+\{[^}]+\}/g).forEach((rule, i) => styleSheet.insertRule(rule, i + 3));
        document.adoptedStyleSheets = [...document.adoptedStyleSheets, styleSheet];
    } catch (e) {
        // Fallback
        const style = document.createElement('style');
        style.type = 'text/css';
        style.id = 'safe-meme-style';
        style.textContent = complexStyles;
        document.head.appendChild(style);
    }
    
    // --- 2. Aplica a tela de fundo (Matrix ou Preto/Verde) ---
    const body = document.body;
    body.setAttribute('data-original-style', body.style.cssText);
    
    if (MATRIX_IMAGE_DATA_URI !== 'COLE_AQUI_SEU_DATA_URI_DA_IMAGEM_MATRIX') {
        body.style.backgroundImage = `url("${MATRIX_IMAGE_DATA_URI}")`;
        body.style.backgroundSize = 'cover';
        body.style.backgroundRepeat = 'repeat';
        body.style.background = '#000';
    } else {
        body.style.background = '#000'; 
        body.style.filter = 'hue-rotate(100deg) saturate(3) contrast(1.5)';
    }
    
    // --- 3. Criação de Elementos (Função Auxiliar) ---
    const createAndAppendElement = (id, styleText, content, isMemeBox = false) => {
        const el = document.createElement('div');
        el.id = id;
        el.className = isMemeBox ? '' : 'matrix-text-style';
        
        let finalStyle = styleText;
        if (isMemeBox) {
            finalStyle += `background: yellow; color: black; font-family: 'Impact', sans-serif; font-weight: bold; border: 4px solid red; box-shadow: 0 0 30px red; font-size: 35px;`;
        }
        
        el.setAttribute('style', finalStyle.replace(/\s+/g, ' '));
        el.textContent = content;
        document.body.appendChild(el);
        return el;
    };

    // --- 4. Elementos da Simulação (9 Janelas + Efeitos de Tela) ---
    
    // Efeitos de Tela
    const glitchBorder = createAndAppendElement('glitch-border', '', '');
    const scanlines = createAndAppendElement('scanlines-overlay', '', '');

    // 1. Centro (Principal)
    const memeBox = createAndAppendElement(
        'safe-meme-box',
        `position: fixed; bottom: 50%; left: 50%; transform: translate(-50%, -50%); padding: 25px; border-radius: 10px; z-index: 999999; cursor: pointer; animation: safeShake 0.4s infinite;`,
        'SISTEMA INVADIDO: [STATUS: ONLINE]',
        true
    );

    // 2. Topo Esquerdo (Decriptação)
    const matrixOverlay = createAndAppendElement(
        'matrix-overlay',
        `position: fixed; top: 10px; left: 10px; width: 350px; white-space: pre-wrap;`,
        `\n>> DECRYPTING FILE: 0x4B3C...\n>> KEY FOUND: F8A79B\n>> ACCESS LEVEL: ADMINISTRATOR\n>> LOGGING USER: TRACE COMPLETE\n`
    );

    // 3. Fundo Direito (Logs)
    const fakeConsole = createAndAppendElement(
        'fake-console-window',
        `position: fixed; bottom: 10px; right: 10px; width: 300px; height: 180px; overflow: hidden; white-space: pre-wrap;`,
        `\n[TASK] Initializing network protocols...\n[TASK] Bypassing firewall: Success!\n[ERROR] Connection instability detected.\n[STATUS] Transfer rate: 99.9%\n`
    );
    
    // 4. Topo Direito (Status do Servidor)
    const logWindow2 = createAndAppendElement(
        'log-window-2',
        `position: fixed; top: 10px; right: 10px; width: 250px; white-space: pre-wrap;`,
        `\nSERVER STATUS:\n\nCPU: 98% (High)\nMEM: 65% (Normal)\nTEMP: 75°C (CRITICAL)\n`
    );

    // 5. Fundo Esquerdo (Mensagem de Ameaça Fake)
    const threatMessage = createAndAppendElement(
        'threat-window',
        `position: fixed; bottom: 10px; left: 10px; width: 350px; white-space: pre-wrap; border-color: red; color: red;`,
        `\n!!! WARNING !!!\n\n[KERNEL PANIC] - DATA WIPE INITIATED.\n(Jk, it's just a joke!)\n\n[Click to end the simulation.]`
    );
    
    // 6. Central Esquerda (Decodificação de Dados)
    const dataDecoder = createAndAppendElement(
        'data-decoder',
        `position: fixed; top: 30%; left: 5%; width: 280px; white-space: pre-wrap;`,
        `\n-- DATA DECODER --\n\n0xABF27 | Decrypted\n0x19C0E | Failed\n0x5D4A2 | Decrypting...\n0x9F3B1 | Decrypted\n`
    );

    // 7. Central Direita (Monitoramento de Pacotes)
    const packetMonitor = createAndAppendElement(
        'packet-monitor',
        `position: fixed; top: 30%; right: 5%; width: 280px; white-space: pre-wrap;`,
        `\n-- PACKET MONITOR --\n\n> TCP: PUSH from 1.1.1.1\n> UDP: ACK to 8.8.8.8\n> ICMP: PING FAILED\n> ARP: REQUEST Sent\n`
    );

    // 8. Meio Superior (Status do Firewall)
    const firewallStatus = createAndAppendElement(
        'firewall-status',
        `position: fixed; top: 10%; left: 50%; transform: translateX(-50%); width: 400px; white-space: pre-wrap; border-color: yellow; color: yellow;`,
        `\n--- FIREWALL STATUS ---\n\nRule 45: BLOCKED\nRule 12: BYPASSED\nRule 99: ACTIVE\n\n[ALL SYSTEMS COMPROMISED]\n`
    );

    // 9. Meio Inferior (Alertas de Segurança)
    const securityAlerts = createAndAppendElement(
        'security-alerts',
        `position: fixed; bottom: 10%; left: 50%; transform: translateX(-50%); width: 450px; white-space: pre-wrap; border-color: red; color: red;`,
        `\n!!! SECURITY ALERT LEVEL 5 !!!\n\n> UNKNOWN THREAD INITIATED\n> LOCATION: UNTRACEABLE\n> ACTION: MANUAL INTERVENTION REQUIRED\n`
    );


    // --- 5. Configuração de Limpeza ---
    const removableElements = [
        memeBox, matrixOverlay, fakeConsole, logWindow2, threatMessage, 
        dataDecoder, packetMonitor, firewallStatus, securityAlerts,
        glitchBorder, scanlines 
    ];
    
    removableElements.forEach(el => {
        // Garante que o clique em qualquer elemento limpe TUDO
        el.addEventListener('click', () => {
            cleanUp();
            console.log("Simulação de hacking de cinema removida e estilos restaurados.");
        });
    });

    console.log("Simulação de hacking de CINEMA injetada! Clique em qualquer painel para remover TUDO e restaurar o fundo.");
})();
