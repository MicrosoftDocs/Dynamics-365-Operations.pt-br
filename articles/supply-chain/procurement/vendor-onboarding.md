---
title: Integração de fornecedores
description: Este tópico descreve o processo de integração de novos fornecedores. Explica as ações necessárias para várias funções durante este processo.
author: mkirknel
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendProspectiveVendorRegistrationRequests,SysUserRequestListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: a7168f9042bae561eb46ecdc8eea377862af8df0
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3203402"
---
# <a name="onboard-vendors"></a>Integração de fornecedores
[!include [banner](../includes/banner.md)]

---

Os novos fornecedores podem ser integrados e registrados como fornecedores no Microsoft Dynamics 365 Supply Chain Management com base nas informações obtidas de uma pessoa que represente o fornecedor.

O processo consiste nas seguintes etapas, onde várias funções executam ações no sistema.

1. **Gerenciamento de dados OData** – Importação de entidade - A solicitação inicial é a de registro do fornecedor potencial. Normalmente, essa solicitação vem de uma origem, como um site hospedado pelo cliente que permite acesso anônimo. Os fornecedores podem se inscreve fornecendo informações básicas, como nome do fornecedor, justificativa, número da organização e nome e o endereço de email da pessoa de contato. As solicitações são importadas por meio da interface de gerenciamento de dados.
2. **Página de listagem da solicitação de inscrição do fornecedor potencial** - Com base nas informações fornecidas na solicitação de inscrição de fornecedor potencial, um profissional de compras decide se o fornecedor deve ser carregado. O profissional de compras exibe a solicitação de entrada na página de listagem **Solicitações de registro de fornecedor potencial**.
3. **Fluxo de trabalho de provisionamento do usuário** - Quando um profissional de compras verifica as informações da entrada e decide continuar com o processo de integração, o fluxo de trabalho de solicitação do usuário provisiona o novo usuário e envia um email de um convite para aceitar a pessoa de contato como um usuário autenticado do Microsoft Dynamics 365.
4. **Assistente de registro de fornecedor** - A pessoa de contato do fornecedor entra usando a nova conta do usuário. Preenche o assistente de registro do fornecedor para fornecer informações como endereços, informações comerciais, categorias de compra e respostas do questionário.
5. **Fluxo de trabalho de aprovaçao** - Uma solicitação do fornecedor que inclui as informações sobre registro é criada. Esta solicitação do fornecedor é enviada a um fluxo de trabalho e é encaminhada para revisão e aprovação.
6. **Criação de um mestre de fornecedor e de modificação da função do usuário** - Quando a solicitação do fornecedor for aprovada, um registro de fornecedor será criado. A conta de usuário da pessoa de contato do fornecedor é permissão concedida para colaboração do fornecedor ou desativada.

A tabela a seguir mostra as etapas e funções que são envolvidas no processo.

| Função e "processo"       | Gerenciamento de dados OData – Importação de entidade | Página de listagem de registro do fornecedor potencial | Fluxo de trabalho do provisionamento de usuário | Assistente de registro de fornecedor | Fluxo de trabalho de aprovação | Criação de um mestre de fornecedor e a função de modificação do usuário |
|--------------------------|---|---|---|---|---|---|
| System                   | A solicitação de um novo fornecedor é importada. | | | | | Depois que a solicitação do fornecedor for aceita, o registro do fornecedor será criado. |
| Profissional de compras | | Inicie o processo de integração. | | | Revise e aceite ou rejeite a solicitação do fornecedor. | |
| Administrador            | | | Crie um usuário no Supply Chain Management e no Microsoft Azure. | | | |
| Pessoa de contato do fornecedor    | | | Envie email à pessoa de contato. | Registre informações do fornecedor. | | |

Para uma demonstração rápida do processo de integração do fornecedor, assista a este breve vídeo no YouTube [sobre como integrar um novo fornecedor no Finance and Operations](https://www.youtube.com/watch?v=0KUc3AGaTKk).

## <a name="importing-the-prospective-vendor-registration-request"></a>Importando a solicitação de inscrição do fornecedor potencial

A solicitação de registro de fornecedor potencial é uma entidade no Supply Chain Management. Você pode configurar o sistema para importar dados por meio da entidade. 

A tabela a seguir mostra as informações que esta entidade contém e que pode ser importada.

| Campo                        | descrição |
|------------------------------|-------------|
| Nome do Fornecedor                  | O nome do fornecedor. |
| Justificativa comercial       | O motivo ou motivos da solicitação do fornecedor. |
| Número da organização          | Um número de registro oficialmente conhecido. |
| Linha de negócio             | A linha de negócio em que o fornecedor está. |
| O nome da pessoa de contato.  | O nome da pessoa que será convidada para registrar informações de fornecedor. |
| Nome do meio da pessoa de contato. | O nome do meio da pessoa que será convidada para registrar informações de fornecedor. |
| O sobrenome da pessoa de contato.   | O sobrenome da pessoa que será convidada para registrar informações de fornecedor. |
| Email da pessoa de contato       | O endereço de email que será usado para criar um novo usuário no Supply Chain Management e que será registrado na conta do Azure Active Directory (Azure AD) do locatário. |
| Data de envio               | A data em que a solicitação foi criada em um sistema externo. |
| Pessoa jurídica em geral                 | A entidade legal na qual o fornecedor deseja se tornar um fornecedor. Esse valor deve ser um código da entidade legal que foi registrado no Supply Chain Management. Se nenhum valor for recebido através do processo de importação, um valor dos parâmetros de Compras será aplicado. |
| Tipo de fornecedor                  | O fornecedor pode ser uma organização ou uma pessoa. O tipo de fornecedor determina como o fornecedor será finalmente criado. |

Depois que a solicitação de inscrição do fornecedor potencial for importada, ela aparecerá na página **Solicitação de registro de fornecedor potencial**. Nesta página de listagem, um profissional de compras poderá convidar o usuário. Uma solicitação de usuário para provisiona o usuário será enviada para um fluxo de trabalho.

## <a name="submitting-a-prospective-vendor-user-request"></a>Enviando uma solicitação de usuário do fornecedor potencial

A finalidade de uma solicitação de usuário fornecedor potencial é provisionar a pessoa que enviou a solicitação inicial, de forma que ela possa entrar no Supply Chain Management usando a conta de email fornecida na solicitação de registro do fornecedor potencial.

A solicitação do usuário fornecedor potencial é processada pelo fluxo de solicitações de usuários. Este fluxo de trabalho se comunica por meio da colaboração do B2B do Azure AD. Ele cria um usuário no Supply Chain Management que tem as configurações de segurança apropriadas.

Os novos usuários que são configurados têm as seguintes funções de segurança:

- Usuário externo do sistema
- Fornecedor potencial (externo)

O novo usuário receberá um email gerado pelo fluxo de trabalho de solicitação de usuários. Esse email convida o usuário para entrar no sistema.

Para obter informações sobre configuração de email e do fluxo de trabalho em geral, consulte a descrição de um fluxo de trabalho de solicitação de usuários [Configurar e manter colaboração de fornecedor](set-up-maintain-vendor-collaboration.md).

## <a name="vendor-registration"></a>Registro de fornecedor

Um usuário fornecedor potencial que entra no Supply Chain Management verá a primeira página do assistente de registro de fornecedor na qual ele poderá inserir as informações do fornecedor.

O assistente reflete a configuração a solicitação de fornecedor. O país ou região onde o fornecedor faz negócios determina quais informações são solicitadas no assistente e quais informações são obrigatórias.

Para obter mais informações sobre a configuração de solicitação de fornecedor, consulte [Configurar e manter colaboração de fornecedor](set-up-maintain-vendor-collaboration.md). A tabela a seguir fornece uma visão geral das páginas do assistente e a finalidade de cada página.

| Página                       | descrição |
|----------------------------|-------------|
| País/região             | O país ou a região determinam a configuração de solicitação de fornecedor que é aplicada nas páginas restantes do assistente. Também determina os valores na pesquisa **Estado de imposto**. |
| Termos e condições       | Essa página pode ficar disponível, dependendo da configuração de solicitação do fornecedor. Se estiver disponível, o usuário deve reconhecer os termos e as condições para continuar. |
| Informações do fornecedor         | Essa página contém o nome do fornecedor, que é inserido automaticamente à solicitação original de registro de fornecedor em potencial. Também contém o número da organização, o número de telefone de fornecedor, número de fax e endereço de email, os endereços de fornecedor para várias finalidades. |
| Informações da pessoa de contato | Essa página contém o nome da pessoa de contato, que é inserido automaticamente à solicitação original de inscrição do fornecedor potencial. Também contém o número de telefone e o endereço de email da pessoa de contato e os endereços da pessoa de contato para várias finalidades. |
| Informações comerciais       | Essa página contém números de registro de imposto (para vários países ou regiões) e os números de funcionários. Também indica se a empresa é de propriedade minoritária. |
| Categorias de compras     | Esta página contém as categorias de compras que o fornecedor está solicitando para aprovação. O usuário pode selecionar categorias na hierarquia de categorias selecionada. Você pode configurar o número de níveis que são exibidos na hierarquia em **Parâmetros de compras** &gt; **Colaboração de fornecedor**, em &gt; **Compras** **Configuração**. |
| Questionários             | O assistente pode incluir um conjunto de questionários para o fornecedor. Os questionários que aparecem no assistente são configurados na solicitação de fornecedor ou por categoria de compras. Se os questionários forem configurados por categoria de compras, as categorias de compras para as quais o fornecedor solicita aprovação determinam os questionários que aparecem no assistente. Na página **Categorias de compras**, você pode adicionar um questionário na categoria relevante e definir o tipo de atividade para **Integração do fornecedor**. |

Quando o usuário do fornecedor potencial conclui o assistente de registro de fornecedor, uma solicitação de fornecedor é criada.

## <a name="manually-or-automatically-submit-a-vendor-request"></a>Enviar uma solicitação de fornecedor manualmente ou automaticamente

Uma solicitação do fornecedor pode ser criada como um rascunho e enviada manualmente a um fluxo de trabalho. Como alternativa, a solicitação de fornecedor pode ser enviada automaticamente a um fluxo de trabalho quando o assistente de registro do fornecedor for concluído. Uma solicitação pode ser enviada manualmente se, por exemplo, um profissional de compras quiser avaliar se a solicitação será encaminhada a um processo de aprovação antes de ser enviada ao fluxo de trabalho.

- Selecione **Parâmetros de compra** &gt; **Colaboração do fornecedor** e selecione **Enviar automaticamente registro de fornecedor potencial para fluxo de trabalho** para configurar a solicitação de fornecedor, de forma que seja enviada automaticamente a um fluxo de trabalho quando o assistente de registro de fornecedor for concluído.

## <a name="vendor-requests"></a>Solicitações do fornecedor

As solicitações de fornecedor disponíveis na página **Solicitações de usuário de colaboração do fornecedor**.

Uma solicitação de fornecedor contém informações que o usuário fornecedor potencial inseriu no assistente de registro do fornecedor.

A solicitação permite revisar informações de fornecedor e decidir se o fornecedor deve se tornar um fornecedor registrado.

A solicitação do fornecedor deve ser enviada a um fluxo de trabalho, e deve ser enviada aos revisores e aprovadores relevantes. Para obter informações básicas sobre como configurar fluxos de trabalho, consulte [Fluxos de trabalho de compras](procurement-sourcing-workflows.md).

A tabela mostra os status que as solicitações de fornecedores podem ter.

| Status                     | descrição |
|----------------------------|-------------|
| Rascunho                      | A solicitação de fornecedor ainda não foi enviada. |
| Solicitação enviada          | A solicitação de fornecedor foi enviada, e a primeira etapa no fluxo de trabalho está sendo processada. |
| Revisão pendente             | Se houver vários revisores em uma tarefa do fluxo de trabalho, um revisor pode aceitar a tarefa de examinar a solicitação do fornecedor e, em seguida, concluir a revisão. Se houver apenas um revisor, este participante pode concluir a revisão selecionando **Concluída** na ação do fluxo de trabalho. Ele não precisa aceitar o item de trabalho primeiro. |
| Solicitação com pendência de aprovação   | A solicitação de fornecedor foi enviada participantes para aprovação, e ha uma opção para solicitar informações adicionais. Uma solicitação para obter informações adicionais faz com que o item de trabalho seja enviado de volta ao emissor. A solicitação do fornecedor também pode ser aprovada ou rejeitada enquanto estiver neste status. |
| Solicitação de alteração do requerimento | Informações adicionais foram solicitadas pelo aprovador, e a solicitação do fornecedor foi enviada para a pessoa que enviou a solicitação de fornecedor. O emissor pode adicionar informações obrigatórias e, em seguida, reenviar a solicitação do fornecedor. Se uma solicitação de fornecedor for reenviada, o status será alterado novamente para **Solicitação com aprovação pendente**. |
| Solicitação aprovada           | Este status será um estado final. |
| Solicitação rejeitada           | Este status será um estado final. |

## <a name="approving-a-vendor-request"></a>Aprovando uma solicitação de fornecedor

Quando uma solicitação de fornecedor for aprovada, uma conta de fornecedor será criada, e o status **Aprovado** aparecerá tanto na solicitação de registro do fornecedor potencial quanto na solicitação de fornecedor.

Antes de aprovar uma solicitação de fornecedor, na página **Novo fornecedor**, na Guia Rápida **Geral**, selecione **Grupo de fornecedores** para selecionar um grupo de fornecedores.

Se o usuário fornecedor potencial tiver acesso ao Supply Chain Management como um usuário de colaboração de fornecedor que represente o fornecedor, defina a permissão de acesso de colaboração de fornecedor como **Sim**. Para desativar a conta de usuário que o fornecedor potencial usou para se registrar, defina essa permissão como **Não**.

Se a permissão de acesso de colaboração de fornecedor for definida como **Sim**, quando a solicitação do fornecedor for aprovada, uma solicitação será enviada para alterar as funções de usuário para que o usuário tenha funções definidas para o tipo de **Fornecedor** em **Funções externas**. Se esta permissão for definida como **Não**, quando a solicitação de fornecedor for aprovada, uma solicitação será enviada para desativar o usuário. Nesse caso, o fluxo de trabalho para desativar uma solicitação do usuário deve ser configurado.

Para uma conta de fornecedor ser criada quando a solicitação do fornecedor for aprovada, a sequência numérica para criar fornecedores das solicitações do fornecedor deverá ser **Automática**.

Para obter uma visão geral das permissões de acesso de um usuário de colaboração de fornecedor, consulte [Configurar e manter colaboração de fornecedor](set-up-maintain-vendor-collaboration.md).

## <a name="rejecting-a-vendor-request"></a>Rejeitando uma solicitação de fornecedor

Se uma solicitação de fornecedor for rejeitada, deverá ser selecionado um motivo para rejeição na solicitação de fornecedor.

Quando uma solicitação de fornecedor foi rejeitada, será enviada uma solicitação para desativar o usuário. Nesse caso, o fluxo de trabalho para desativar uma solicitação do usuário deve ser configurado. Para obter mais informações, consulte [Configurar e manter colaboração de fornecedor](set-up-maintain-vendor-collaboration.md).

Quando uma solicitação de fornecedor for rejeitada, o status **Rejeitado** aparecerá tanto na solicitação de registro do fornecedor potencial quanto na solicitação de fornecedor.

## <a name="deleting-a-prospective-vendor-registration-request-in-various-statuses"></a>Excluir uma solicitação de registro do fornecedor potencial em diversos status

Os vários status de uma solicitação de registro do fornecedor potencial fornece uma visão geral do andamento da solicitação.

Usando a ação **Excluir** da solicitação de registro do fornecedor potencial, você pode limpar e remover a cadeia de registros criada, e pode desativar a conta do usuário. O resultado da ação **Excluir** varia, dependendo do status de solicitação de registro do cliente potencial, conforme mostrado na tabela a seguir.


|          Status          |                                                                                     Descrição do status                                                                                      |                                                                                                                                                            Resultado da ação de exclusão                                                                                                                                                             |
|--------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|           Nova            |                                                                         Nenhuma ação foi tomada em relação à solicitação.                                                                          |                                                                                                                                              A solicitação de registro do fornecedor potencial foi excluída.                                                                                                                                               |
|      Solicitado pelo usuário      | Quando você selecionar <strong>Convidar usuário</strong>, o status será alterado para <strong>Solicitado pelo usuário</strong>, e uma solicitação de usuário potencial é criada e enviada a um fluxo de trabalho do usuário. |                                                                                                          Você não pode excluir uma solicitação de registro de cliente potencial com este status, pois o fluxo de trabalho da solicitação do usuário não foi concluído.                                                                                                          |
|       Usuário convidado       |                                                               O fluxo de trabalho da solicitaçãodo usuário foi aprovado e o usuário foi criado.                                                               |                                                                                                                      Uma solicitação para desativar o usuário foi criada e a solicitação de registro do fornecedor potencial foi excluída.                                                                                                                      |
| Registro em andamento |                                                         O novo usuário se conectou e iniciou o assistente de registro de fornecedor.                                                          |                                                                                     Uma solicitação para desativar o usuário for criada e a solicitação de registro do fornecedor potencial e os dados que foram inseridos no assistente de registro do fornecedor foram excluídos.                                                                                      |
|  Solicitação de fornecedor criada  |                                                                     O assistente de registro de fornecedor foi concluído.                                                                      | Uma solicitação para desativar o usuário foi criada, e a solicitação de registro do fornecedor potencial, os dados que foram inseridos no assistente de registro do fornecedor e a solicitação de fornecedor foram excluídos.<blockquote>[!NOTE]<br>Você não pode usar a ação <strong>Excluir</strong> quando a solicitação do fornecedor estiver em um processo de revisão no fluxo de trabalho.</blockquote> |
|         Aprovada         |                                                                               A solicitação do fornecedor foi aprovada.                                                                               |                                                                                                   A solicitação de registro do fornecedor potencial, os dados que foram inseridos no assistente de registro do fornecedor e a solicitação do fornecedor foram excluídos.                                                                                                    |
|         Rejeitada         |                                                                               A solicitação do fornecedor foi rejeitada.                                                                               |                                                                                                   A solicitação de registro do fornecedor potencial, os dados que foram inseridos no assistente de registro do fornecedor e a solicitação do fornecedor foram excluídos.                                                                                                    |

