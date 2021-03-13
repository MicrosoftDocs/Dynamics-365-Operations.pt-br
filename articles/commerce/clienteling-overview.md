---
title: Visão geral de depoimentos de clientes
description: Este tópico mostra uma visão geral dos novos recursos de depoimentos de clientes disponíveis no aplicativo de loja.
author: bebeale
manager: AnnBe
ms.date: 01/29/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2018-10-01
ms.dyn365.ops.version: Version 10.0.7
ms.openlocfilehash: 206031f5ddbaedb2b581a452fe8979252647f0c4
ms.sourcegitcommit: 872600103d2a444d78963867e5e0cdc62e68c3ec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2021
ms.locfileid: "5097246"
---
# <a name="clienteling-overview"></a>Visão geral de clientes

[!include [banner](includes/banner.md)]


Muitos varejistas, principalmente os especializados em tecnologia de ponta, querem que seus representantes de vendas estabeleçam relacionamentos duradouros com seus principais clientes. Os representantes devem saber do que os clientes gostam e não gostam, o histórico de compras, as preferências em termos de produtos, além de datas importantes, como aniversários e bodas. Os representantes precisam de um lugar onde possam capturar essas informações e encontrá-las com facilidade quando necessário. Se essas informações estiverem disponíveis em uma única exibição, os associados poderão selecionar facilmente os clientes que atendem a critérios específicos. Por exemplo, eles podem localizar todos os clientes que preferem comprar bolsas ou aqueles que têm um evento importante próximo, como um aniversário ou uma boda.

## <a name="client-book"></a>Catálogo de clientes

No Microsoft Dynamics 365 Commerce, os varejistas podem usar a funcionalidade de registro de clientes para ajudar os representantes a desenvolver relacionamentos de longo prazo com seus principais clientes.

O registro de clientes inclui cartões de clientes que mostram as informações de contato de cada cliente, com mais três propriedades definidas pelo varejista e configuradas na sede. Os varejistas podem escolher as três coisas mais importantes que os representantes de vendas devem saber sobre os clientes. Por exemplo, um joalheiro pode incluir datas importantes, como aniversários ou bodas, que são ocasiões em que as pessoas podem querer comprar joias. Da mesma forma, um varejista de moda pode querer incluir os itens de interesse e as marcas preferidas dos clientes.

Usando o registro de clientes, os representantes também podem filtrar a lista para mostrar apenas os clientes que atendem a critérios específicos. Por exemplo, a loja recebeu uma nova coleção de sapatos, e um representante quer informar aos clientes que gostam de comprar calçados. Nesse caso, ele pode filtrar o registro de clientes para localizar os clientes relevantes e realizar outras ações.

Quando um cliente deixa de ser considerado principal por algum motivo e, portanto, não deve mais ser gerenciado de perto, os representantes de vendas podem removê-lo do registro de clientes.

Alguns varejistas não querem gerenciar os clientes no nível do representante de vendas. Eles querem gerenciar uma lista dos principais clientes no nível da loja. Esses varejistas podem ver os clientes nos registros de clientes da loja. Usando esta opção, eles podem ver os clientes nos registros de clientes de todos os representantes de vendas cujo catálogo de endereços corresponde ao catálogo de endereços da loja atual. Assim, se um representante trabalha em várias lojas da entidade legal, o registro de clientes mostra os clientes de todas essas lojas. Esta funcionalidade é compatível com mais recursos. Por exemplo, é possível reatribuir clientes de um representante de vendas para outro. Este recurso é útil quando os representantes são transferidos ou saem da empresa.

Cada representante de vendas pode ter um registro de clientes por entidade legal e pode adicionar um ou mais clientes ao seu registro de clientes. No Commerce, hoje cada cliente só pode ser adicionado a um registro de clientes. No entanto, a Microsoft pretende adicionar uma funcionalidade que permite que um único cliente seja incluído em vários registros de clientes.

> [!NOTE]
> Diferentemente da pesquisa de cliente, o registro de clientes não filtra os registros de clientes com base nos catálogos de endereços da loja.

## <a name="activities-and-notes"></a>Atividades e anotações

Os canais online oferecem aos varejistas maneiras de saber quais são as preferências dos clientes sem que eles tenham de fornecer essas informações explicitamente. Por outro lado, quando os clientes interagem com os representantes de vendas na loja, eles compartilham explicitamente informações sobre suas preferências. Infelizmente, essas informações podem ser perdidas depois que a venda é concluída. Porém, quando registradas, elas podem ajudar os varejistas a entender melhor os clientes e também a fazer recomendações melhores e oferecer uma experiência melhor de compra.

Para obter informações críticas compartilhadas pelos clientes, os representantes de vendas podem usar não apenas os atributos do registro de clientes mas também a funcionalidade de atividades e anotações. Os varejistas podem configurar os tipos de atividade, como informações sobre visitas à loja, endereço de email, número de telefone e compromissos. As atividades criadas pelos representantes podem ser vistas no formato de linha do tempo no ponto de venda (POS). Elas também podem ser vistas na guia **Atividades** da página **Todos os clientes \> Geral** do Headquarters.

Os representantes de vendas também podem usar anotações para obter informações genéricas dos clientes e consultá-las antes de cada interação. Essas anotações são salvas no Headquarters e podem ser vistas no perfil do cliente ou na página de detalhes do cliente no call center.

> [!NOTE]
> No momento, todas as anotações e atividades podem ser vistas por qualquer representante de vendas que trabalha para a entidade legal e que pode ver as páginas de detalhes dos clientes. As anotações e atividades não ficam restritas aos representantes que adicionaram o cliente ao registro de clientes.

## <a name="integration-with-dynamics-365-customer-insights"></a>Integração ao Dynamics 365 Customer Insights

Usando o aplicativo Dynamics 365 Customer Insights, os varejistas podem agregar dados de vários sistemas que os clientes usam para interagir com a marca do varejista. Eles podem usar esses dados para gerar uma exibição única do cliente e para derivar informações. A integração do Customer Insights com o Commerce permite que os varejistas selecionem uma ou mais medidas que devem ser mostradas no cartão do cliente no registro de clientes. Por exemplo, os varejistas podem usar os dados no Customer Insights para calcular a “probabilidade de rotatividade” de um cliente e definir “a próxima melhor ação”. Se esses valores forem definidos como medidas, poderão ver vistos no cartão do cliente e fornecer informações cruciais para os representantes de vendas. Para obter mais informações sobre o Customer Insights, consulte a documentação do [Dynamics 365 Customer Insights](https://docs.microsoft.com/dynamics365/ai/customer-insights/overview). Para obter mais informações sobre medidas. consulte [Medidas](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures).

## <a name="set-up-clienteling"></a>Configurar os depoimentos de clientes

Para ativar a funcionalidade de depoimentos de clientes no seu ambiente, siga estas etapas.

1. No espaço de trabalho **Gerenciamento de recursos**, filtre os recursos pelo módulo **Varejo e comércio**.

    ![Depoimentos de clientes na lista de recursos do módulo Comércio](./media/Enable_clienteling.png "Depoimentos de clientes na lista de recursos do módulo Varejo e comércio")

2. Para ativar o recurso **Depoimentos de clientes**, selecione **Habilitar agora**.
3. Na página **Parâmetros de Comércio**, na guia **Sequência numérica**, selecione a linha **Identificador do registro de clientes**. Depois, no campo **Código da sequência numérica**, selecione uma sequência numérica. O sistema usará essa sequência numérica para atribuir um ID aos registros de clientes.
4. Selecione **Salvar**.
5. Crie um novo grupo de atributos contendo os atributos que você quer obter dos clientes que são gerenciados nos registros de clientes. Para obter instruções, consulte [Atributos e grupos de atributos](https://docs.microsoft.com/dynamics365/retail/attribute-attributegroups-lifecycle).

    - Defina os atributos necessários como **Pode ser refinado**. Os representantes de vendas podem usar esses atributos para filtrar o registro de clientes.
    - Defina a ordem de exibição desses atributos. Essa ordem de exibição determina quais atributos devem ser mostrados no cartão do cliente no registro de clientes. Uma ordem de exibição 1 é considerada mais alta que uma ordem de exibição 2. Portanto, o atributo que tem uma ordem de exibição 1 será mostrado antes do atributo com ordem de exibição 2.

    > [!NOTE]
    > Você pode tornar o Customer Insights disponível na mesma página. Porém, é necessário criar um ID do aplicativo Azure e um segredo para fins de autenticação. (Para obter informações sobre os requisitos, consulte a seção [Ativar a integração do Customer Insights com o Commerce](#turn-on-the-integration-of-customer-insights-with-commerce) mais adiante neste tópico.) Se o Customer Insights estiver ativado e você selecionar uma ou mais medidas que devem ser mostradas no cartão do cliente, essas medidas serão mostradas primeiro. Em seguida, serão mostrados grupos de atributos do registro de clientes com base na ordem de exibição. Por exemplo, se você selecionar duas medidas do Customer Insights, essas duas medidas e um atributo do registro de clientes serão mostrados no cartão do cliente. (O atributo do registro de clientes a ser mostrado será o que tem a ordem de exibição mais alta.)

6. Na página **Parâmetros de comércio**, na guia **Depoimentos de clientes**, no campo **Grupo de atributos do registro de clientes**, selecione o grupo de atributos que você acabou de criar.

    ![Grupo de atributos selecionado do registro de clientes](./media/Client%20book%20attributes.png "Grupo de atributos selecionado do registro de clientes")

7. Para capturar atividades que ocorrem no PDV, defina os tipos de atividade na página **Tipos de atividade** (**Varejo e Comércio \> Clientes \> Tipos de atividade**).

    > [!NOTE]
    > Os tipos de atividade são obtidos pelo Commerce Scale Unit quando ele faz uma chamada em tempo real pela primeira vez. Depois que as atividades são obtidas, ficam armazenadas em cache por algumas horas. Se você alterar os tipos de atividade, espere até que o cache não seja mais válido. Se preferir, no caso de ambientes que não são de produção, reinicie o serviço Commerce Scale Unit.

8. Adicione dois botões no layout da tela apropriada do PDV para que os representantes de vendas possam ver o próprio registro de clientes e o registro de clientes da loja. (Os registros de clientes da loja incluem clientes de todos os registros de clientes de todos os representantes que compartilham um catálogo de endereços com a loja.) As operações correspondentes são denominadas **Exibir clientes no registro de clientes** e **Exibir clientes nos registros de clientes da loja**, respectivamente. Há três operações adicionais disponíveis relacionadas a registros de clientes. Essas operações determinam quais representantes podem adicionar, remover e reatribuir clientes do registro de clientes. São elas **Adicionar cliente ao registro de clientes**, **Remover clientes do registro de clientes** e **Reatribuir clientes a um registro de clientes**, respectivamente.
9. Execute os seguintes trabalhos da agenda de distribuição: 1040, 1150, 1110 e 1090.

Depois que você concluir este procedimento, os representantes de vendas poderão abrir a página de detalhes do cliente no PDV e adicionar clientes ao seu registro de clientes, ver e capturar atividades e anotações de clientes e selecionar clientes usando atributos do cliente e do registro de clientes para filtrar o registro de clientes. A ilustração a seguir mostra um exemplo de registro de clientes.

![Exemplo de registro de clientes](./media/client_book.png "Exemplo de registro de clientes")

## <a name="turn-on-the-integration-of-customer-insights-with-commerce"></a>Ativar a integração do Customer Insights com o Commerce

Para ativar a integração do Customer Insights com o Commerce, você deve verificar se tem uma instância ativa do Customer Insights no inquilino onde o Commerce está provisionado. Você também deve ter uma conta de usuário do Azure Active Directory (Azure AD) com uma assinatura do Azure.

Siga estas etapas para configurar a integração.

1. No portal do Azure, registre um novo aplicativo e anote o nome do aplicativo, a ID do aplicativo e o segredo. Essas informações serão usadas para autenticação de serviço a serviço entre o Commerce e o Customer Insights. Anote o segredo com segurança, pois ele será necessário para salvá-lo no cofre de chaves. Para o exemplo a seguir, use CI_Access_name, CI_Access_AppID, CI_Access_Secret para o nome do aplicativo, a ID do aplicativo e o segredo, respectivamente. Para obter mais informações, consulte [Início rápido: Registrar um aplicativo na plataforma de identidade da Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).

    > [!IMPORTANT]
    > Execute as etapas para lembrar de mudar o segredo antes que ele expire. Do contrário, a integração será interrompida inesperadamente.

2. Vá para a instância do Customer Insights e procure o nome do aplicativo criado acima (neste exemplo, "CI_Access_name").
3. Crie um Azure Key Vault e anote o nome e a URL (neste exemplo, "keyvaultname", "KeyVaultURL"). Para obter instruções, consulte [Início rápido: Definir e recuperar um segredo do Azure Key Vault usando o portal do Azure](https://docs.microsoft.com/azure/key-vault/quick-create-portal).
4. Salve o segredo (neste exemplo, "CI_Access_Secret") no cofre. Quando esse segredo é armazenado no cofre, o segredo recebe um nome. Observe o nome do segredo (neste exemplo, 'SecretName').
5. Para acessar o segredo do Azure Key Vault, você precisará criar outro aplicativo com uma ID e um segredo do aplicativo (neste exemplo, "KeyVault_Access_AppID" e "KeyVault_Access_Secret"). Observe o segredo com segurança, pois ele não será exibido novamente.
6. Em seguida, você precisará conceder permissões ao aplicativo para acessar o Key Vault do Commerce usando APIs. Vá para página de aplicativo no portal do Azure. Na seção **Gerenciar**, selecione **Permissões de API**. Adicione a permissão para acessar o **Azure Key Vault**. Para essa permissão, selecione **Política de acesso**. Selecione o modelo como **Gerenciamento secreto** e selecione as opções **Obter**, **Listar**, **Descriptografar** e **Criptografar**. 
5. Na sede do Commerce, vá para **Administração do sistema \> Configuração \> Parâmetros do Key Vault** e insira as informações necessárias para o Key Vault. Em seguida, no campo **Cliente do Key Vault**, insira a ID do aplicativo usado na etapa 4 para que o Commerce possa acessar os segredos no Key Vault.
6. Para adicionar o aplicativo criado na etapa 1 à lista de aplicativos seguros (também chamada de lista de confiança), vá para o Customer Insights e selecione **Exibir** ao aplicativo. Para obter instruções, consulte [Permissões](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-permissions).
7. Na página **Administração do sistema > Configuração > Parâmetros de Key Vault** do Commerce HQ, atualize os campos como descrito a seguir: 

- **URL do Key Vault**: "KeyVaultURL" (da etapa 3 acima).
- **Cliente do Key Vault**: "KeyVault_Access_AppID" (da etapa 5 acima).
- **Chave secreta do Key Vault**: "KeyVault_Access_Secret" (da etapa 5 acima).
- Na seção **Segredos**:
    - **Nome**: qualquer nome; por exemplo, "CISecret".
    - **Descrição**: qualquer valor.
    - **Segredo**: **cofre**://<Name of key vault>/<name of secret>> Neste exemplo, ele será "vault://KeyVaultName/SecretName".

Depois de atualizar os campos, selecione **Validar** para garantir que o segredo possa ser acessado pelo aplicativo Commerce.

8. No Commerce, na página **Parâmetros do Commerce**, na guia **Clientes**, na FastTab **Dynamics 365 Customer Insights**, defina a **ID do aplicativo** como "CI_Access_AppID" (da etapa 1 acima). Em **Nome do segredo**, selecione o nome do segredo inserido na etapa 7 acima ("CISecret"). Defina a opção **Habilitar Customer Insights** como **Sim**. Se, por algum motivo, a configuração for malsucedida, uma mensagem de erro será exibida e a opção será definida como **Não**. 

Você pode ter vários ambientes no Customer Insights, como o de teste e o de produção. No campo **ID da instância de ambiente**, insira o ambiente apropriado. No campo **ID de cliente alternativo**, informe a propriedade no Customer Insights que está mapeada para o número da conta do cliente. (No Commerce, o número da conta do cliente é a ID do cliente.) As três propriedades restantes são as medidas que serão mostradas no cartão de cliente no registro do cliente. É possível selecionar até três medidas a serem exibidas no cartão do cliente. No entanto, não é necessário selecionar medidas. Como mencionado antes, o sistema mostra esses valores primeiro e, depois, mostra os valores para o grupo de atributos de registro de clientes.
