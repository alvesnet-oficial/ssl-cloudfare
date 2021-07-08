# ssl-cloudfare

Proporciona uma series de camadas de segurança ao seu site que proporciona um mecanismo de busca melhor nas pesquisas do google, implantando uma nuvem de proxy utilizando a estrutura a nuvem do cloudfare.

- O cloudfare não faz cache de banco de dados
- Mas faz cache de arquivos staticos exemplos: html, css e js
- Se as informações de produto que voce está atualizando no seu site não está atualizando é porque voce está utilizando um 'cache de 
- Cloudfare não é totalmente gratuito. Para sites comerciais (.com, .com.br, .net) ele possuem algus recursos gratuito. Para sites .org não permite utilizar recursos gratuito como instituição educacional e do governo.


# SS/TLS:

Algumas hospedagem trabalha com algumas dessa modalidade abaixo, teremos que consultar nosso provedor de hospedagem:

Desligado (não seguro): Nenhuma criptografia aplicada

Flexível: Criptografa o tráfego entre o navegador e o Cloudflare

Completo: Criptografa de ponta a ponta usando um certificado autoassinado no servidor

Completo (estrito): Criptografa de ponta a ponta, mas requer um certificado CA confiável ou CA de origem do Cloudflare no servidor

# SS/TLS\Certificado de Borda:

Para ter uma segurança ainda maior com o site seguir os passos abaixo:

Sempre usar HTTPS - (Ativar)

* Redirecione todas as solicitações com o esquema “http” para “https”. Isso se aplica a todas as solicitações http para a zona.

# HTTP Strict Transport Security (HSTS)\Alterar Ajustes da de HSTS:

* Aplicar a política de segurança da Web para o seu site.

Habilitar HSTS (Strict-Transport-Security) - (Ativar)

* Forneça cabeçalhos HSTS com todas as solicitações HTTPS

Cabeçalho de idade máxima (max-age) - (Ativar 1 mês)

* Especifique a duração em cache dos cabeçalhos HSTS nos navegadores

Aplicar política de HSTS a subdomínios (includeSubDomains) - (Ativar)

* Todos os domínios abaixo dele herdarão os mesmos cabeçalhos HSTS
Atenção: Se algum dos seus subdomínios não suportar HTTPS, ele se tornará inacessível.


Pré-carga - (Ativar)
Permitir que os navegadores pré-carreguem a configuração do HSTS automaticamente
Atenção: A pré-carga pode tornar um site sem suporte HTTPS completamente inacessível.

Plataforma sem sniff - (Ativar)
Envie o cabeçalho “X-Content-Type-Options: nosniff” para evitar que o Internet Explorer e o Google Chrome façam o sniff de MIME fora do Tipo de conteúdo declarado.

# Firewall:

Proteção para seu site.

# Firewall\Bots:

Modo de combate a bots - (Ativar)

* Solicitações de desafio que correspondem aos padrões de bots conhecidos antes de eles acessarem o seu site.

# Speed:

Otimizações ao seu site.

# Speed\Otimizações: 

Minificação Automática - (Ativar)


JavaScript (x)

CSS (x)

HTML (x)

Reduza o tamanho do arquivo do código-fonte no seu site.

Nota: Limpe o cache para que sua alteração entre em vigor imediatamente.

Esta configuração foi alterada pela última vez há poucos segundos

Brotli - (Ativar)
Acelere os tempos de carregamento de página para o tráfego HTTPS do visitante aplicando a compactação Brotli.

***Otimização automática de plataformas para o WordPress - APO - (Analisar como instalar esse plugin no Worpress...)***

***Rocket Loader™ - (Alerta não ativar esse recurso pois ele é incompativel com o elementor) ***

***Móvel - (Alerta não ativar esse recurso pois ele pode quebrar o seu site ***
URL AMP real
Exiba o URL real do seu site em suas páginas AMP, em vez do URL tradicional do cache do Google AMP.
Melhore o tempo de pintura para páginas que incluem JavaScript.






















