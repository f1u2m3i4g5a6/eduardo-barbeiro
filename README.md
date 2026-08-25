# EDUARDO • D'MASA V23 — CONTROL CENTER

Baseada no index atual enviado pelo usuário e preservando Agenda, Blog, Chat, Horários, Conteúdo, Avaliações e recursos anteriores.

## Painel > Site
Edita e salva no Firestore:
- nome do site e sigla
- subtítulo e descrição SEO
- textos do Hero
- selos do Hero
- textos do studio
- WhatsApp
- comodidades e pagamentos
- logo por URL ou upload sem Firebase Storage
- cores: principal, destaque, fundo, cards, texto e texto secundário
- presets Red, Blue Steel, Emerald, Gold e Violet
- prévia instantânea antes de salvar

## Painel > Equipe
- adicionar profissional
- foto, nome, especialidade, avaliação e ordem
- criar usuário e senha inicial
- editar perfil
- trocar acesso (novo usuário/senha)
- desativar profissional

### Segurança das senhas
Senhas nunca são gravadas no Firestore e nunca são exibidas pelo painel.
O Firebase Authentication não permite que um site cliente leia a senha existente de outra conta.
Por isso, “Trocar acesso” cria uma nova credencial e revoga o acesso profissional anterior no Firestore.
O profissional também pode trocar a própria senha usando a senha atual.

## Painel profissional
O profissional entra pelo mesmo formulário de login do site.
Ele vê “Minha agenda” e pode:
- ver somente os próprios agendamentos
- concluir atendimentos
- cancelar os próprios horários
- falar com o cliente por WhatsApp
- trocar a própria senha

Ele NÃO tem acesso a Equipe, Site, Catálogo, Blog, Conteúdo, Chat administrativo, Clientes gerais, Horários globais ou Bloqueios.

## Painel > Catálogo
- criar/editar/desativar serviços
- preço, duração, ordem e imagem
- criar/editar/desativar planos
- benefícios e destaque

## Firestore novo
Criado automaticamente quando usado:
- settings/site
- staff/{uid}
- professionals/{id}
- services/{id}
- subscriptions/{id}

## Instalação obrigatória
1. Substitua index.html
2. Firebase > Firestore Database > Regras
3. Substitua tudo pelo firestore.rules deste pacote
4. Clique em Publicar
5. Faça Ctrl + Shift + R no site

Firebase Authentication > Email/Senha precisa continuar ativado.
Firebase Storage não é necessário.
