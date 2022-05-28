---
title: Gerenciar parceiros de negócios B2B usando hierarquias do cliente
description: Este tópico descreve como usar hierarquias de clientes para gerenciar parceiros de negócios para sites de comércio eletrônico entre empresas (B2B) do Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 02/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 70acdf469be2fcddd9e2bf755e958c1b20ee2fcf
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8686562"
---
# <a name="manage-b2b-business-partners-using-customer-hierarchies"></a>Gerenciar parceiros de negócios B2B usando hierarquias do cliente

[!include [banner](../../includes/banner.md)]

Este tópico descreve como usar hierarquias de clientes para gerenciar parceiros de negócios para sites de comércio eletrônico entre empresas (B2B) do Microsoft Dynamics 365 Commerce.

Na sede do Commerce, uma entidade *hierarquia do cliente* é usada para representar as organizações parceiras de negócios que usarão seu site de comércio eletrônico B2B. Antes de começar a usar hierarquias de cliente para gerenciar parceiros de negócios, habilite os recursos de comércio eletrônico B2B na sede do Commerce e defina uma sequência numérica para a hierarquia do cliente.

## <a name="enable-the-b2b-e-commerce-feature-in-commerce-headquarters"></a>Habilitar recurso de comércio eletrônico B2B na sede do Commerce

Para usar os recursos de comércio eletrônico B2B, primeiro ative o recurso **Habilitar o uso de recursos de comércio eletrônico B2B** na sede do Commerce.

1. Acesse **Espaços de trabalho \> Gerenciamento de recursos**.
1. Na guia **Tudo**, use a caixa de filtro para procurar **Módulo: varejo e comércio**.
1. Localize o recurso **Habilitar o uso de recursos de comércio eletrônico B2B** e selecione **Habilitar agora** no canto inferior direito.

## <a name="define-a-number-sequence-for-the-customer-hierarchy"></a>Definir uma sequência numérica para a hierarquia do cliente

As sequências numéricas são usadas para gerar identificadores exclusivos legíveis para registros de dados mestres e registros de transações que exigem identificadores. Você deve definir uma sequência numérica que será usada para gerar a ID da hierarquia do cliente. Para obter mais informações sobre sequências numéricas, consulte [Visão geral de sequências numéricas](/dynamics365/fin-ops-core/fin-ops/organization-administration/number-sequence-overview).

Para definir uma sequência numérica para a hierarquia do cliente na sede do Commerce, siga estas etapas.

1. Acesse **Varejo e comércio \> Configuração da sede \> Sequências numéricas \> Sequências numéricas**.
1. Crie uma nova sequência numérica ou selecione uma existente para reutilizá-la.
1. Vá para **Varejo e Comércio \> Configuração da sede \> Parâmetros \> Parâmetros compartilhados com o comércio**.
1. Na guia **Sequências numéricas**, adicione a sequência numérica criada ou selecionada antes da referência de **ID da hierarquia do cliente**.

![A sequência numérica adicionada à referência de ID da hierarquia do cliente.](../media/NumberSequenceCustHierarchy.png)

## <a name="how-the-approval-process-works"></a>Como funciona o processo de aprovação

Quando um parceiro de negócios solicita o ingresso em um site de comércio eletrônico B2B, o sistema salva a solicitação como um *cliente potencial*. Uma pessoa da sede do Commerce, como um gerente de operações de varejo, pode aprovar ou rejeitar solicitações de parceiros. Para obter mais informações sobre como gerenciar solicitações de parceiros de negócios e aprovações de clientes potenciais, consulte [Gerenciar usuários de parceiros de negócios em sites de comércio eletrônico B2B](manage-b2b-users.md).

Quando um cliente potencial é aprovado, o sistema cria dois registros novos de cliente:

- Um registro de cliente do tipo **Organização** representa a organização que deseja se tornar um parceiro de negócios.
- Um registro de cliente do tipo **Pessoa** representa a pessoa que enviou a solicitação.

Além disso, um novo registro de hierarquia do cliente é criado em **Varejo e Comércio \> Clientes \> Hierarquias de cliente**. Este registro de hierarquia do cliente tem as seguintes propriedades:

- **ID da hierarquia do cliente** – a ID exclusiva da hierarquia do cliente. Essa ID usa a sequência numérica definida em parâmetros compartilhados do Commerce.
- **Nome** – o nome da organização parceira comercial, conforme especificado na solicitação de integração. Este campo é editável.
- **Finalidade** – esta propriedade é definida como o valor predefinido da **organização B2B**.
- **Organização** – a ID de cliente da organização do parceiro de negócios.

A pessoa que enviou a solicitação de integração é adicionada na FastTab **Hierarquia** e a função **Administrador** é atribuída a ela. À medida que o administrador adiciona mais usuários à organização do parceiro de negócios em um site B2B, um novo registro de cliente é criado para cada usuário. O registro de cliente também é adicionado ao registro de hierarquia de cliente relevante para o parceiro de negócios e a função **Usuário** é atribuída a ele.

### <a name="examples"></a>Exemplos

Uma pessoa com o nome Sam J. envia uma solicitação de integração em nome da organização Microsoft. Depois que a solicitação é aprovada, duas novas contas de clientes são criadas: uma do tipo **Pessoa** para Sam J e uma do tipos **Organização** para Microsoft.

Como mostrado na ilustração a seguir, um novo registro de hierarquia de cliente também é criado. O nome desse registro é igual ao da organização (**Microsoft**), e a função **Administrador** é atribuída a Sam J. como administrador. Sam J. adiciona outros usuários da Microsoft do site B2B a essa hierarquia e atribui o **Usuário** a eles. Neste exemplo, Sush R. foi adicionado como um usuário.

![Exemplo de um registro de hierarquia de cliente.](../media/CustomerHierarchy2.png)

Para determinar se um cliente está associado a uma hierarquia de cliente, abra o registro do cliente. Como mostra a ilustração a seguir, o campo **ID da hierarquia do cliente** na seção **B2B** na FastTab **Varejo** mostra se o cliente faz parte de uma hierarquia de cliente. A opção **Administrador de B2B** indica se o cliente é um administrador dessa hierarquia.

![Exemplo da seção B2B na FastTab Varejo de um registro de cliente, em que o cliente é associado a uma hierarquia e especificado como um administrador.](../media/CustomerHierarchyMapping2.png)

Na maioria dos casos, os valores de propriedade de todos os registros de cliente em uma hierarquia devem coincidir. Por exemplo, como todos os usuários parceiros comerciais devem obter preços semelhantes para produtos, seu grupo de preços e configurações associadas devem coincidir. No entanto, o sistema não impõe essa consistência. Portanto, os usuários da sede do Commerce relevantes são responsáveis por garantir que os valores de propriedade e as configurações correspondam a todos os clientes em determinada hierarquia.

Os usuários da sede do Commerce podem inspecionar valores de propriedade de todos os registros de clientes em uma hierarquia em um modo de exibição lado a lado. Como mostra a ilustração a seguir, você pode usar a opção **Geral** na lista suspensa na FastTab **Hierarquia** e selecionar uma seção do registro de cliente para mostrar as propriedades relacionadas. Os usuários podem editar os valores de propriedade diretamente neste modo de exibição. Para copiar todos os valores de um registro de cliente administrador para todos os usuários, selecione **Substituir** na FastTab **Hierarquia**.

![Exemplo de um registro de hierarquia de cliente, mostrando o botão Substituir e a opção na lista suspensa.](../media/HierarchyDetails2.png)

[!include [footer-include](../../includes/footer-banner.md)]
