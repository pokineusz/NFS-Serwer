Cel projektu
Celem projektu było skonfigurowanie serwera NFS i klienta NFS w środowisku VirtualBox, zapewniając szyfrowanie połączenia poprzez stunnel (TLS).
________________________________________
Środowisko
•	Serwer NFS 
•	Klient NFS 
•	Obie maszyny wirtualne działające na Ubuntu Server
________________________________________
Wykonane kroki
I. Konfiguracja serwera NFS 
1.	Zainstalowano nfs-kernel-server.
2.	Utworzono katalogi /exports/backup i /exports/documents.
3.	Skonfigurowano /etc/exports dla udostępniania zasobów.
4.	Uruchomiono i przetestowano usługę NFS.
II.  Konfiguracja klienta NFS (nfsclient)
1.	Zainstalowano nfs-common i autofs.
2.	Skonfigurowano /etc/auto.master i /etc/auto.nfs do automatycznego montowania zasobów.
3.	Sprawdzono poprawność montowania i dostępność plików.
III. Szyfrowanie NFS przez TLS (stunnel)
1.	Zainstalowano stunnel4 na serwerze i kliencie.
2.	Wygenerowano certyfikaty (nfs_server.pem, nfs_client.pem).
3.	Skonfigurowano stunnel na serwerze (/etc/stunnel/nfs_server.conf) i kliencie (/etc/stunnel/nfs_client.conf).
4.	Testowano działanie stunnel, korygując błędy w uprawnieniach i konfiguracji.
IV Automatyzacja startu usług (rc.local)
1.	Utworzono i skonfigurowano skrypt /etc/rc.local.
2. Skrypt został dostosowany do automatycznego restartu autofs oraz stunnel po starcie systemu.
3. Zmieniono uprawnienia (chmod +x /etc/rc.local) i włączono usługę rc-local.service, aby działała przy każdym uruchomieniu systemu.

