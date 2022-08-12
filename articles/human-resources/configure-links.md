---
title: Criar links do Human Resources para outro ambiente
description: Este artigo explica como criar um link do Microsoft Dynamics 365 Human Resources para outro ambiente do Dynamics 365.
author: twheeloc
ms.date: 03/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-29-11
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9640f460ed7b0b1a0cfdffb7c318bf833f8627fc
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9065283"
---
# <a name="create-links-from-human-resources-to-another-finance-environment"></a>Criar links do Human Resources para outro ambiente do Finance

Um cliente pode ter dois ambientes do Dynamics 365 nos quais estão trabalhando. Por exemplo, o cliente pode ter um ambiente do Dynamics 365 Human Resources na infraestrutura do Finance e precisa se conectar a outro ambiente do Dynamics 365 Finance. 

Este recurso permitirá links de uma página do Human Resources para uma página específica em outro ambiente do Finance. Quando os links são configurados, você pode especificar onde o link estará disponível no Human Resources e a página de destino que será aberta no outro ambiente.

> [!Note] 
> Você deve ativar os **Aprimoramentos da experiência do usuário de recursos humanos** no **Gerenciamento de recursos** para obter este recurso.

## <a name="configure-target-systems"></a>Configurar sistemas de destino

No Human Resources, os administradores de sistema podem definir links que serão exibidos nas páginas do **Human Resources**. Partes da configuração são os ambientes do Finance para os quais você deseja navegar como o destino do link. 

Para configurar o sistema de destino:
1. Na página **Configurar links**, selecione **Configurar sistema de destino**.  
2. Insira o nome do sistema de destino e forneça a URL de ambiente do Finance. Após configurar sistemas de destino, você pode definir os links.

## <a name="configure-links"></a>Configurar links

Cada link criado terá as seguintes informações definidas:
 - **Link**: o nome do link. Usado apenas para identificação.
 - **Habilitar esse link**: defina como **Sim** para exibir o link para os usuários do Human Resources.
 - **Nome para exibição**: defina o nome que aparecerá como um link para o ambiente secundário. 
 - **Exibir link no formulário**: escolha em qual página gostaria de exibir o link. Os links só podem ser reproduzidos no espaço de trabalho de **Autoatendimento para funcionários** e nas páginas **Trabalho**, **Cargo**, **Trabalhador** e **Trabalhador simplificado**.
 - **Grupo**: é possível organizar os links usando grupos. Selecione um grupo existente ou crie um novo usando a coluna **Grupo**.
 - **Sistema de destino**: selecione o sistema de destino criado usando a opção **Configurar o sistema de destino**. Este será o ambiente secundário que será usado ao navegar usando o link.
 - **Use a empresa atual de usuário**: Selecione **Sim** se deseja usar a empresa atual do usuário ao navegar para o Finance. Escolha **Não** para selecionar a empresa que deverá ser usada.
 - Item de menu **Destino** - digite o item de menu do ambiente do Finance que o link deve usar ao navegar. Itens de menu onde você pode navegar diretamente estão disponíveis. 

   Para localizar o item de menu necessário:
   1. Acesse o ambiente do Finance e a página que é o destino da navegação. 
   2. Copie o item de menu da URL. Por exemplo, se desejar que o link execute a lista de funcionários em finanças e operações, insira o valor que aparece após "&mi" na URL. 
   3. O item de menu para navegar para a página de listagem de funcionário neste exemplo é: HcmWorkerListPage_Employees.

 - **Link para fonte de dados**: selecione a fonte de dados com o qual o link está fazendo referência. As origens mais comuns como **Trabalhador** e **Posição** estão disponíveis.

### <a name="access-to-links"></a>Acesso a links

Os administradores de sistema verão links recém-criados em páginas definidas se a opção **Habilitar esse link** estiver definida como **Não**. Isso pode ser usado antes testando links para aparecerem para outros funcionários. Todas funções restantes considerarão links configurados somente depois que a opção **Habilitar esse link** estiver definida como **Sim**. Os funcionários que têm acesso a páginas dos links terão acesso aos links.

Os usuários também devem ter direitos de segurança no ambiente secundário definido para acessar as páginas nesse ambiente. Se não tiverem, uma caixa de diálogo de segurança será exibida usando o link.


