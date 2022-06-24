---
title: Gerenciamento de clientes em lojas
description: Este artigo explica como os varejistas podem habilitar os recursos de gerenciamento de clientes no ponto de venda (PDV) no Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 12/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 805d0b5894b18e2fc34f481bdc32ada7a4b1aee0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8863478"
---
# <a name="customer-management-in-stores"></a>Gerenciamento de clientes em lojas

[!include [banner](includes/banner.md)]

Este artigo explica como os varejistas podem habilitar os recursos de gerenciamento de clientes no ponto de venda (PDV) no Microsoft Dynamics 365 Commerce.

É importante que os associados da loja possam criar e editar registros de clientes no PDV. Dessa forma, eles podem capturar qualquer atualização para informações do cliente, como o endereço de email, o número de telefone e o endereço. Essas informações são úteis em sistemas downstream, como marketing, pois a eficácia desses sistemas depende da precisão dos dados do cliente.

Os associados de vendas podem disparar o fluxo de trabalho de criação de clientes de dois pontos de entrada de PDV. Eles podem selecionar um botão que esteja mapeado para a operação **Adição do cliente** ou podem selecionar **Criar cliente** na barra de aplicativos na página de resultados da pesquisa. Em ambos os casos, a caixa de diálogo **Novo cliente** é exibida, na qual os associados de vendas podem inserir os detalhes necessários do cliente, como o nome do cliente, o endereço de email, o número de telefone, o endereço e as informações adicionais relevantes ao negócio. Essas informações adicionais podem ser capturadas usando os atributos do cliente associados ao cliente. Para obter mais informações sobre atributos de cliente, consulte [Atributos de cliente](dev-itpro/customer-attributes.md).

Os associados de vendas também podem capturar endereços de email e números de telefone secundários. Além disso, eles podem capturar a preferência do cliente no recebimento de informações de marketing por meio de qualquer um desses endereços de email ou números de telefone secundários. Para habilitar esse recurso, os varejistas devem ativar o recurso **Capturar vários emails e números de telefone e consentimento para marketing sobre esses contatos** no espaço de trabalho **Gerenciamento de recursos** no Commerce headquarters (**Administração de sistemas \> Espaços de trabalho \> Gerenciamento de recursos**).

## <a name="default-customer-properties"></a>Propriedades padrão do cliente

Os varejistas podem usar a página **Todas as lojas** no Commerce headquarters (**Varejo e Comércio \> Canais \> Lojas**) para associar um cliente padrão a cada loja. O Commerce então copia as propriedades definidas para o cliente padrão para todos os novos registros de cliente que são criados. Por exemplo, a caixa de diálogo **Criar cliente** mostra as propriedades herdadas do cliente padrão associado à loja. Essas propriedades incluem o **tipo de cliente**, **grupo de clientes**, **opção de recibo**, **e-mail de recibo**, **moeda** e **idioma**. Quaisquer **afiliações** (agrupamentos de clientes) também são herdadas do cliente padrão. Porém, as **dimensões financeiras** são herdadas do grupo de clientes associado ao cliente padrão, e não do próprio cliente padrão.

> [!NOTE]
> O **valor do email** será copiado do cliente padrão somente se a ID do email de recebimento não for fornecida para os clientes recentemente criados. Isso significa que, se a ID do email de recebimento estiver presente no cliente padrão, todos os clientes criados no site de comércio eletrônico receberão a mesma ID de email, já que não há interface do usuário para capturar a ID de email do recibo do cliente. É recomendável deixar o campo **email de recibo** em branco para o cliente padrão da loja e usá-lo somente se você tiver um processo de negócios que dependa de um endereço de email de recebimento presente. 

Os associados de vendas podem capturar vários endereços para um cliente. O nome e o número de telefone do cliente são herdados das informações de contato associadas a cada endereço. A Guia Rápida **Endereços** de um registro de cliente inclui um campo **Finalidade** que os associados de vendas podem editar. Se o tipo de cliente for **Pessoa**, o valor padrão será **Residência**. Se o tipo de cliente for **Organização**, o valor padrão será **Empresa**. Outros valores para os quais esse campo oferece suporte incluem: **Residência**, **Escritório** e **Caixa postal**. O valor do campo **País** para um endereço é herdado do endereço principal especificado na página **Unidade operacional** do Commerce headquarters em **Administração da organização \> Organizações \> Unidades operacionais**.



## <a name="additional-resources"></a>Recursos adicionais

[Modo de criação de cliente assíncrono](async-customer-mode.md)

[Converter clientes assíncronos em clientes síncronos](convert-async-to-sync.md)

[Atributos de clientes](dev-itpro/customer-attributes.md)

[Exclusão de dados offline](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion)
