# troubleshooting_1

#Troubleshooting de redes

##PROBLEMA: empresa teve seu ambiente danificado por funcionario demitido.

##OBJETIVO: restabelecer o mais prontamente possivel a infraestrutura do cliente.

Modelo de Referência ISO/OSI - Modelo de 7 camadas

TOP-DOWN
  7- Aplicação (Application) | Navegador | Apache2 | FTP 
  6- Apresentação (Presentation) | Codificação
  5- Sessão (Session) | Manutenção
  4- Transporte (Transport) | TCP/UDP (TCP: Transmission Control Protocol) | (UDP: User Datagram Protocol) | Porta lógica 
  3- Rede (Net) | IP | Roteador (Domínio de Broadcast)	
  2- Enlace (Data Link/Frame) | MAC/LLC | Switch (Domínio de colisão)
  1- Física (Phisical) - Conectorização | Repetidor/HUB

PREMISSA - TÉCNICAS
	  - Rede: 172.31.xx.0/24;
	  - Realizar um snapshot da maquina virtual;
	  - Realizar cópia (backup) de todo arquivo de configuração a ser alterado;
	  - Estado dos serviços que serão analisados;
	  - LOG de sistema: 
	    	Alternar o terminal do Debian
		    	alt+F(1-6)
		    Entrar no terminal 6
			    alt+F6
		    Mostrar as últimas 1000 linhas do arquivo de LOG 
		    	#tail -f -n 1000 /var/log/syslog
			
#SRVLNX-NAIROBI
  FÍSICA (Virtualização - VirtualBox)
	      Import das máquinas virtuais
  	Confuguração das Interfaces de rede (NIC)
	    	A1 - NAT
	    	A2 - Rede Interna (LAN Segment)
  	Conexões de Switch	
		    Rede Interna (LAN Segment)
	
  LÓGICO (Sistema Operacional)
	  Configuração base
	  	  Hostname
		Interface(s) de rede
			  /etc/network/interfaces
			  A1 - NAT | enp0s17 | dhcp
			  A2 - Rede Interna | enp0s8 | static
		Usuário/Grupo
			  /etc/passwd
		Outra*
	Serviços
	  	Acesso remoto (openssh-server)
		  Roteador/NAT (Network Address Translation)
		Web
			#Arquivo das portas padroes do serviço
		
		DNS (bind9)
			#Qrquivo com a declaração das zonas existentes
			//etc/bind/named/conf.local
			
			#Arquivos com a entrada das zonas DIRETAS  declaradas no named.conf.local
			/etc/bind/db.nairobi00.com.br
			
			##Arquivo com a entrada das zonas REVERSA declaradas no named.conf.local
			/etc/bind/db.reverso.nairobi00.com.br
			
		DHCP
	
SRVWIN-RIO		

FÍSICA (Virtualização - VirtualBox)
	Import das máquinas virtuais
	Confuguração das Interfaces de rede (RIC)
	Conexões de Switch	
	
LÓGICO (Sistema Operacional)
	Configuração base
		Hostname
		Interface(s) de rede
		Usuário/Grupo
		Outra*
	Serviços
		Acesso remoto
		DHCP
		
CLTWIN-OSLO
FÍSICA (Virtualização - VirtualBox)
	Import das máquinas virtuais
	Confuguração das Interfaces de rede (NIC)
		A1 - Rede Interna - LAN Segment
	Conexões de Switch	
		LAN Segment
	
LÓGICO (Sistema Operacional)
	Configuração base
		Hostname
			hostname
		Interface(s) de rede
			ncpa.cpl
		Usuário/Grupo
			lusrmgr.msc
		Outra*
	Serviços
		Acesso remoto
			sysdm.cpl
		Roteador/NAT (Network Address Translation)
		Web
		DNS











