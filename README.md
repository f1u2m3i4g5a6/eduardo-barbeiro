# EDUARDO • D'MASA V22 ULTRA — BLOG + CHAT EM TEMPO REAL

Esta versão preserva a agenda, horários editáveis, painel, fotos, avaliações, autenticação e todos os recursos anteriores.

## Novo: Blog administrável

No site:
- seção D'MASA Journal
- artigos de autocuidado, cabelo, barba e estilo
- artigo em tela premium
- compartilhamento
- imagens com fallback
- responsivo em celular, tablet e desktop

No Painel > Blog:
- novo artigo
- editar artigo
- excluir artigo
- título
- categoria
- resumo
- texto completo
- publicado ou rascunho
- foto por URL
- foto enviada do computador/celular
- compressão automática sem Firebase Storage
- busca e filtro

O arquivo enviado é convertido e otimizado no navegador antes de ser salvo no Firestore.

## Novo: Chat em tempo real

No site:
- botão Chat ao vivo ao lado de Agendar
- atalho de Chat
- Chat na navegação inferior
- seção completa no meio da página
- mensagens em tempo real
- histórico por usuário
- mensagens privadas
- avisos de mensagem não lida
- frases rápidas
- limite de 800 caracteres

No Painel > Chat:
- lista de clientes
- novas mensagens em tempo real
- indicador de não lidas
- busca de conversa
- resposta ao cliente
- botão WhatsApp quando o telefone estiver disponível
- histórico de mensagens

Cada usuário só consegue acessar a própria conversa. A conta administrativa consegue responder a todas.

## Firestore usado pela V22

Novas estruturas:
- blogPosts/{postId}
- chatThreads/{uid}
- chatThreads/{uid}/messages/{messageId}

Você NÃO precisa criar as coleções manualmente.

## O que precisa atualizar

OBRIGATÓRIO:
1. substituir o index.html
2. Firestore Database > Regras
3. substituir pelas regras do firestore.rules da V22
4. clicar em Publicar
5. Ctrl + Shift + R

Não é necessário Firebase Storage.
Não é necessário plano Blaze.
Não é necessário criar índices adicionais para Blog ou Chat.

## Segurança

Blog:
- leitura pública
- somente administrador pode escrever

Chat:
- cliente autenticado só lê/escreve a própria conversa
- cliente não consegue ler conversas de outros usuários
- somente administrador consegue acessar todas as conversas
- mensagens de cliente são validadas como senderRole=customer
- mensagens não podem ser editadas/deletadas pelo cliente

## Imagens

Continuam funcionando imagens locais como:
- imagens/cabelo.png
- imagens/barba.png
- imagens/cabelo-barba.png
- imagens/completo.png
- imagens/corte1.png ... corte6.png

As fotos enviadas pelo Painel > Blog são salvas como imagem otimizada dentro do próprio documento do artigo.
