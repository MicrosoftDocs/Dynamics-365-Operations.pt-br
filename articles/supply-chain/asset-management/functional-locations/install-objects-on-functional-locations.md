---
title: Instalar ativos em locais funcionais
description: Este tópico explica como instalar ativos em locais funcionais em Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 06/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetFunctionalLocationObjectChange, EntAssetFunctionalLocationObjectInstall, EntAssetFunctionalLocationObject
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 85b9f473cc725896a00501510eea02d7cfb21782
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422075"
---
# <a name="install-assets-on-functional-locations"></a>Instalar ativos em locais funcionais

[!include [banner](../../includes/banner.md)]

 

Após criar estruturas de locais funcionais, a próxima etapa será instalar ativos nos locais funcionais relevantes. Este tópico explica como instalar ativos nesses locais funcionais em Gerenciamento de Ativos. Para obter informações sobre como criar ativos, consulte [Introdução aos ativos](../objects/introduction-to-objects.md).

Se você criou uma estrutura de ativos, a estrutura de ativos inteira deverá ser instalada em um local funcional. Portanto, apenas os ativos pai (ativos em nível superior sem ativos pai) podem ser selecionadas em um local funcional. Todos os ativos filho relacionados (subativos) também serão instalados no local funcional. Quando você instala ativos em um local funcional, as dimensões financeiras do local funcional devem ser transferidas automaticamente para eles, dependendo da configuração no tipo de local funcional selecionado para o local funcional. Para obter mais informações sobre como configurar tipos de locais funcionais, consulte [Tipos de locais funcionais](../setup-for-functional-locations/functional-location-types.md).

> [!NOTE]
> Você pode configurar tipos de ativo no tipo de local funcional que é usado para um local funcional. Nesse caso, quando você instala ativos no local funcional, somente os ativos pai com o mesmo tipo de ativo são mostrados na lista de ativos que pode ser instalada no local funcional.

Depois de instalar ativos em um local funcional, você pode substituir um ativo pai ou uma estrutura de ativo conforme necessário. Assim como ocorre na instalação de ativos, você selecione um ativo pai para substituir. Todos os ativos filho relacionadas também serão substituídos. 


## <a name="install-an-asset-structure-on-a-functional-location"></a>Instale uma estrutura de ativo em um local funcional

1. Selecione **Gerenciamento de ativos** \> **Comum** \> **Locais funcionais** \> **Todos os locais funcionais** ou **Locais funcionais ativos**.
2. Selecione o local funcional para instalar um ativo.
3. Selecione **Instalar ativo**.

    A seção **Atributos** mostra uma lista dos requisitos de atributos de ativos configurados no tipo de local funcional selecionado para o local funcional. Os atributos são meramente informativos. O sistema não valida os atributos em relação aos atributos de ativos configurados no ativo que você está instalando. Você deve fazer essa validação após selecionar um ativo no campo **Ativo**.

4. No campo **Ativo**, selecione o ativo pai para instalar. Todos os ativos filho relacionadas são automaticamente incluídos na instalação.

    A seção **Atributos de ativo** à direita da lista de ativos mostra os atributos de ativos que são relacionadas aos ativos selecionados.

5. No campo **Efetivo**, selecione a data e a hora a partir da qual a instalação de ativos é válida. Após essa data e hora, os custos do ativo e subativos relacionadas serão relacionados ao local funcional.

    > [!NOTE]
    > Os atributos de ativos configurados nos ativos são adicionados à seção **Atributos**. Por exemplo, o requisito de atributo **Peso** foi adicionado como uma requisição no ativo e no local funcional. Se o ativo tiver requisitos de atributos do mesmo tipo que o local funcional, os valores dos requisitos de atributo do ativo serão inseridos nos campos **Valor**. Portanto, você pode validar os valores de ativos nos requisitos de atributos que são configurados no local funcional. Os requisitos de atributos configurados no local funcional são marcados com uma marca de seleção.

6. Selecione **OK**.

    > [!NOTE]
    > Para alterar a instalação de um ativo, instalando-o em um novo local funcional, siga as etapas 1 a 6 deste procedimento. Quando você instala um ativo em um novo local funcional, o ativo é desinstalado automaticamente do local funcional anterior. Todas as solicitações de manutenção ou ordens de serviço criadas no ativo antes antes de sua instalação em um novo local funcional **não** são transferidas automaticamente para o novo local funcional. Se essas solicitações de manutenção e ordens de serviço ainda forem necessárias para o ativo, você deverá recriá-las manualmente depois que o ativo for instalado no novo local.

7. Para exibir uma lista de todos os ativos, inclusive os subativos, que são instalados na local funcional, selecione o local funcional na página **Todos os locais funcionais** e, depois, selecione **Ativos**.
8. Para exibir uma lista de solicitações de manutenção de ativos, ordens de serviço ativas ou registros com falhas relacionados aos ativos que estão instalados em um local funcional, selecione o local funcional na página **Todos os locais funcionais** e, depois, **Solicitações**, **Ordens de serviço** ou **Falhas**.

> [!NOTE]
> Quando os dados relacionados a ativos forem alterados, eles serão atualizados automaticamente no local funcional em que o ativo foi instalado. Essa atualização automática refere-se a alterações em solicitações de manutenção, ordens de serviço, registros de falhas em ativos, registros de tempo de inatividade de manutenção e registros de medida de ativos.

## <a name="automatically-create-one-asset-on-a-functional-location"></a>Criar automaticamente um ativo em um local funcional

Você pode configurar estágios de local funcional e tipos de local funcional para manipular a criação automática de *um* ativo em um local funcional. O ativo tem a mesma ID e nome que o local funcional. Essa funcionalidade pode ser útil quando se trata da manutenção em um ativo grande, estático, como um edifício.

Para poder criar automaticamente um ativo em um local funcional, os seguintes dados de configuração devem estar disponíveis:

- Crie um tipo de local funcional para manipular a criação automática de um ativo. No campo **Tipo de ativo**, selecione um tipo de ativo. Para obter mais informações, consulte [Tipos de local funcional](../setup-for-functional-locations/functional-location-types.md).
- Crie um estado de ciclo de vida do local funcional para manipular a criação automática de um ativo. Defina a opção **Criar ativo** como **Sim**. Para obter mais informações, consulte [Estados de ciclo de vida de local funcional](../setup-for-functional-locations/functional-location-stages.md).

Após a disponibilização dos dados de configuração, você estará pronto para criar um ativo.

1. Na página **Todos os locais funcionais**, verifique se o local funcional em que você deseja que o ativo seja automaticamente criado utiliza o tipo de local funcional criado com essa finalidade.
2. Selecione o local funcional na lista.
3. Selecione **Atualizar o estado do local funcional**. Depois, selecione o estado de ciclo de vida criado com essa finalidade. Um ativo é instalado automaticamente agora no local funcional. Esse ativo tem o mesmo nome que o local funcional.
