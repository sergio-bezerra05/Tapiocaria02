# Tapiocaria — versão mobile local

Esta pasta contém uma PWA estática para celular. O app registra pedidos, vendas, cardápio e ajustes no IndexedDB do navegador. Pedidos, cardápio e ajustes usam localStorage como cópia de compatibilidade; as vendas detalhadas ficam em uma tabela própria do IndexedDB. Não precisa da API `/api/ajustes` nem de funções do Netlify.

## Como abrir e instalar

O app precisa ser publicado em HTTPS para instalar como PWA e usar o cache offline. Publique o conteúdo desta pasta em qualquer hospedagem estática; não é necessário configurar funções ou banco em nuvem. Depois, abra o endereço no celular:

- Android: Chrome → menu → **Instalar app** ou **Adicionar à tela inicial**.
- iPhone: Safari → **Compartilhar** → **Adicionar à Tela de Início**.

Abra o app com internet uma vez para baixar o cache. Depois disso, os pedidos, pagamentos e relatórios continuam disponíveis sem conexão. Os dados ficam neste navegador e aparelho, sem sincronização automática com outros dispositivos. Se o app já foi usado no mesmo domínio e navegador, a primeira abertura copia os dados existentes para o IndexedDB local.

O gerador de QR do Pix é carregado de um CDN quando há internet. Sem conexão, o código Pix copia e cola continua disponível, mas o QR pode não aparecer. Notificações ntfy também dependem de internet.

O banco fica sujeito às políticas de armazenamento do navegador. A exportação CSV do relatório serve para guardar as vendas; faça cópias regulares fora do aparelho.
