---
title: Contratar candidatos com grupos de talento no Attract
description: Este tópico explica como criar e configurar grupos de talentos no Microsoft Dynamics 365 Talent - Attract.
author: andreabichsel
manager: AnnBe
ms.date: 06/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: e00a54db50f1360096bb5329eef660927cecde3d
ms.sourcegitcommit: 4359e7e4eec25362df61c9a26c7218604d12da3d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2020
ms.locfileid: "3078034"
---
# <a name="source-candidates-with-talent-pools-in-attract"></a>Contratar candidatos com grupos de talento no Attract

[!include [banner](includes/banner.md)]

Os recrutadores e gerentes de contratação podem organizar seus candidatos usando a funcionalidade grupos de talentos no Attract. Os grupos de talentos podem ajudar a controlar e a se envolver com todos os candidatos a posições em sua empresa.

## <a name="create-and-share-a-talent-pool"></a>Criar e compartilhar um grupo de talentos

Qualquer usuário que tenha a função de recrutador, gerente de contratação ou administrador do Attract poderá criar grupos de talentos. O proprietário de um grupo de talentos também pode compartilhar o grupo com outros usuários de forma que grupos de usuários, especialmente recrutadores, possam procurar em um grupo de candidatos compartilhado.

Os colaboradores de um grupo de talentos podem exibir a lista de candidatos desse grupo. Eles também podem adicionar candidatos ao grupo ou remover candidatos dele.

Siga as etapas abaixo para criar e compartilhar um grupo de talentos.

1. Na home page do Attract, no painel esquerdo de navegação, selecione **Grupos de Talentos**.

    A guia **Meus de grupos de talentos** mostram todos os grupos de talentos aos quais você tem acesso, com detalhes sobre cada um. Os detalhes incluem o proprietário do grupo e o número de candidatos nele.

1. No canto superior direito da página, selecione **Novo** para abrir a caixa de diálogo **Criar grupo de talentos**.
1. Insira um nome exclusivo para o grupo de talentos.
1. Para adicionar pessoas como colaboradores ao grupo, encontre seus nomes usando o seletor de pessoas e então adicione-as à lista. Você só pode compartilhar um grupo de talentos com os usuários que tenham a função recrutador, gerente de contratação ou administrador do Attract.
1. Selecione **Adicionar** para criar o grupo de talentos.
     > [!NOTE]
     > Como alternativa, você pode adicionar colaboradores a um grupo de talentos depois de criá-lo. Você também pode gerenciar o acesso a um grupo de talentos. Por exemplo, é possível revogar o acesso de um usuário ao grupo de talentos.
     > - Para adicionar colaboradores a um grupo de talentos existente cujo proprietário seja você, na guia **Meus grupos de talentos**, no canto superior direito do cartão do grupo de talentos, selecione o botão de reticências (**...**) e então selecione **Editar**. Localize as pessoas usando o seletor de pessoas e então as adicione à lista. 
     > - Para revogar o acesso de um usuário ao grupo de talentos, no canto superior direito do cartão do grupo de talentos, selecione o botão (**...**) e então selecione **Editar**. Na guia **Gerenciar o acesso**, selecione o botão de lixeira ao lado do usuário.

6. Selecione **Atualizar** para concluir e salvar a operação.

> [!NOTE]
> Para criar mais de um grupo de talentos, sua organização deve ter o complemento Contratação Abrangente.

## <a name="add-and-remove-candidates"></a>Adicionar e remover candidatos

O proprietário e os colaboradores do grupo de talentos podem adicionar candidatos, exibir os candidatos contidos nele e remover candidatos dele.

1. Na guia **Meus grupos de talentos**, selecione um grupo de talentos para abri-lo.

    Será mostrada uma lista dos candidatos que fazem parte do grupo de talentos.

1. Para adicionar candidatos ao grupo de talentos, selecione **+ Novo** no canto superior direito para abrir a caixa de diálogo **Adicionar candidato** e então siga um dos procedimentos abaixo.

    - Para adicionar um candidato interno, você poderá pesquisar a pessoa por endereço de email. Depois que uma busca bem-sucedida, o endereço de email do candidato, o nome e o sobrenome serão preenchidos. Se você tiver o currículo ou qualquer documento relacionado do candidato, poderá carregá-los neste momento. Em seguida, selecione **Adicionar** para adicionar o candidato ao grupo de talentos.
    - Para adicionar um candidato externo, insira manualmente seu endereço de email, nome e sobrenome. Se você tiver o currículo ou qualquer documento relacionado do candidato, poderá carregá-los neste momento. Em seguida, selecione **Adicionar** para adicionar o candidato ao grupo de talentos.
    - Para adicionar vários candidatos, selecione a guia **Do Excel**. Você poderá baixar o modelo apropriado do Microsoft Excel, inserir os detalhes dos candidatos, salvar a planilha e carregá-la no aplicativo.

        Se algum erro for encontrado na planilha, você receberá mensagens sobre eles. Você poderá corrigir os erros e tentar carregar a planilha novamente. Quando nenhum outro erro for encontrado, selecione **Adicionar** para carregar a planilha. A planilha é processada em segundo plano e você será notificado quando todos os candidatos tiverem sido adicionados ao grupo de talentos.

1. Para remover um candidato já existente do grupo de talentos, na coluna **Ação**, selecione o botão de lixeira para o candidato.

## <a name="search-and-view-candidate-profiles"></a>Pesquisar e exibir perfis do candidato

> [!NOTE] 
> Este recurso está atualmente em visualização. Se quiser experimentá-lo, você deverá [ativá-lo nas configurações do administrador do Attract](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature). 

Os grupos de talentos permitem a você exibir o perfil, as informações do LinkedIn, os documentos relacionados e o histórico de solicitação de emprego do candidato. Você pode pesquisar todo o banco de dados de todos os candidatos adicionados a qualquer grupo de talentos, inclusive candidatos fechados e ativos.

>[!NOTE]
> Quando você adiciona novos candidatos, as novas adições podem levar 15 minutos até serem indexadas para pesquisa.

Com a experiência de pesquisa aprimorada, você pode pesquisar todos os documentos dos candidatos e filtrar por medalhistas de prata, origens, habilidades, formação educacional e muito mais. Em versões anteriores, era necessário especificar a entidade a ser pesquisada. Agora, o Attract pode pesquisar todos os campos relacionados a candidatos e classificar os resultados.

1. Para iniciar uma nova pesquisa pelo banco de dados de candidatos, digite o texto que deseja pesquisar na caixa de pesquisa, na guia **Grupos de talentos**. 

Você pode digitar o nome do candidato ou quaisquer atributos que esteja procurando. Para separar atributos, use um espaço.

Você pode restringir os resultados, alterando sua consulta de pesquisa ou usando os filtros inteligentes no lado esquerdo da página.

Os resultados da pesquisa mostram os destaques dos vários atributos que correspondem à sua consulta de pesquisa. Selecione qualquer candidato no qual esteja interessado para exibir seu perfil.

### <a name="syntax-highlights"></a>Destaques de sintaxe 

| Operador | Utilização                                                      | Exemplo              |
|----------|------------------------------------------------------------|----------------------|
| \*       | Pesquisas de subcadeias; podem ser usadas para fornecer todos os registros | Entrada: Mi\* <br></br> Resultado: todos os registros contendo campos que começam com "Mi", como Microsoft, Micro Systems, Midtown Enterprises ou Middleton <br></br>Entrada: \* <br></br> Resultado: todos os registros no banco de dados |
| ""       | Pesquisas de correspondência exata                                | Entrada: "Microsoft" <br></br> Resultado: todos os registros que contenham "Microsoft"                    |

>[!WARNING]
> Não desative a pesquisa por relevância para sua instância do Common Data Service. Isso desabilitará a experiência de pesquisa no Attract.

Todas os usuários têm uma exibição comum dos perfis de candidato. A guia **Perfil** mostra todas as informações sobre habilidades, experiência profissional e formação educacional que o candidato forneceu como parte de sua solicitação de emprego usando o portal de carreiras.

- Você pode exibir os detalhes de contato do candidato. Você também pode editar ou atualizar as informações conforme o necessário usando o botão **Editar detalhes**.

- Você pode exibir o histórico completo de solicitação de emprego do candidato. Você pode ver todas as solicitações de emprego do candidato em sua organização e o status delas. Se você fizer parte da equipe de contratação para uma posição de trabalho, poderá selecionar **Exibir** para examinar em detalhes a solicitação de emprego.

- A guia **Documentos** mostra todos os documentos que o candidato adicionou de seu perfil ou durante as solicitações de emprego. Você pode usar esta guia, por exemplo, para gerenciar os currículos, as cartas de apresentação e o trabalho de portfólio do candidato. Você também pode usar esta guia para adicionar documentos.

    Para exibir um documento, selecione o nome do documento na lista de documentos. Você pode exibir documentos do Microsoft Word no aplicativo usando o Microsoft Office 365. Você também pode baixar os documentos para o computador local usando a opção **Download** para cada documento.

- A guia **LinkedIn** mostra informações do candidato no LinkedIn. Para usar esta guia, é necessário conectar a conta do LinkedIn nas configurações do usuário, e a conexão com o LinkedIn Recruiter do seu ambiente deve ser estabelecida. Para obter mais informações, consulte [Contratar candidatos com o LinkedIn Recruiter no Microsoft Dynamics 365 Talent - Attract](./attract-linkedin-recruiter.md).

> [!NOTE]
> Somente os candidatos podem atualizar suas habilidades, histórico de formação educacional e experiência de trabalho.

## <a name="add-candidates-from-a-talent-pool-to-a-job"></a>Adicionar candidatos de um grupo de talentos a um trabalho

Dos resultados da pesquisa ou de um grupo de talentos, você pode enviar por push um candidato a qualquer trabalho ativo para o qual esteja contratando. Para enviar por push um candidato a um trabalho específico, siga estas etapas.

1. Localize o candidato usando a opção de pesquisa e então abra seu perfil. Como alternativa, abra o pool de talentos da guia **Meus grupos de talentos**, procure o candidato no seu grupo de talentos e então abra o perfil dele.

1. Na página do perfil do candidato, selecione **Adicionar ao trabalho** no canto superior direito. 
     
     Uma lista de trabalhos para os quais você faz parte da equipe de contratação, como recrutador ou como gerente de contratação, é mostrada.

1. Selecione o trabalho ao qual o candidato será adicionado e então selecione **Adicionar**. Também é possível pesquisar o trabalho usando o campo de pesquisa na parte superior da caixa de diálogo **Adicionar candidato a trabalho**.

    Se a prospecção tiver sido habilitada para o trabalho, o candidato será adicionado ao estágio **Cliente potencial**.

    Se a prospecção não tiver sido habilitada para o trabalho, o candidato será adicionado ao estágio **Aplicar**. Dependendo da configuração do trabalho, o candidato também poderá receber um email onde poderá ver sua solicitação de emprego.

## <a name="add-candidates-from-a-job-to-a-talent-pool"></a>Adicionar candidatos de um trabalho a um grupo de talentos

Geralmente, vários bons candidatos para um trabalho não são selecionados, mas você não deseja perder o contato deles. Nesse caso, você pode adicionar os candidatos a um grupo de talentos para poder convidá-los a concorrer a próximos trabalhos.

1. Ir para trabalho ao qual você deseja adicionar um candidato.

1. Selecione o candidato e abra a solicitação de emprego dele.

1. Na página de solicitação de emprego, selecione **Adicionar a grupo de talentos**. Uma lista de grupos de talentos aos quais você tem acesso é mostrada.

1. Selecione ou pesquise o grupo de talentos e então selecione **Adicionar** para adicionar o candidato a ele.
