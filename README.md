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
