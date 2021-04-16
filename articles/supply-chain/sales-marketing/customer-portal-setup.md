---
title: Instalar, configurar e atualizar o portal do cliente
description: Este tópico oferece detalhes de licenciamento e instruções de configuração para o portal do cliente.
author: dasani-madipalli
ms.date: 06/08/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: dcb952ccc68f5f19119f8b72285667e259b00429
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840716"
---
# <a name="install-set-up-and-update-the-customer-portal"></a>Instalar, configurar e atualizar o portal do cliente

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

## <a name="licensing-requirements"></a>Requisitos de licenciamento

Para implementar o portal do cliente, você deve ter as seguintes licenças:

- Portais do **Power Apps** – essa licença é necessária para hospedar o portal do cliente. Os portais são licenciados com base no uso. Para obter mais informações, consulte os [requisitos de licenciamento de portais do Power Apps](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq#portals).
- **Gravação dupla** – você deve ter as licenças necessárias para habilitar a gravação dupla para tabelas do Supply Chain Management. Para obter mais informações, consulte os [requisitos do sistema para gravação dupla](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-system-req.md).

## <a name="dependencies-on-dual-write-and-power-apps-portals"></a>Dependências de gravação dupla e de portais do Power Apps

O portal do cliente depende de portais do Power Apps e da gravação dupla, conforme mostrado na ilustração a seguir.

![Dependências do portal do cliente](media/customer-portal-elements.png "Dependências do portal do cliente")

Diferente de outros recursos do Supply Chain Management, o modelo de portal do cliente reside em portais do Power Apps. Portanto, o portal do cliente é limitado pela funcionalidade e recursos fornecidos pelos portais do Power Apps e pelas tabelas em gravação dupla.

## <a name="required-setup-to-enable-the-customer-portal"></a><a name="required-setup"></a>Configuração necessária para habilitar o portal do cliente

Após verificar que tem as licenças necessárias, você pode configurar a gravação dupla, conforme descrito nas [instruções de sincronização inicial de gravação dupla](../../fin-ops-core/dev-itpro/data-entities/dual-write/initial-sync.md).

Certifique-se de habilitar os seguintes mapeamentos de tabela em gravação dupla:

- Cabeçalho de ordem de venda
- Detalhes de ordem de venda
- Contas
- Contatos
- Produtos

Após a conclusão dessa configuração, você poderá provisionar o modelo de portal do cliente.

## <a name="provision-the-customer-portal"></a>Provisione o portal do cliente

Antes de começar, verifique se você já concluiu a [configuração necessária](#required-setup). Em seguida, siga estas etapas para provisionar o portal do cliente.

1. Vá para [make.powerapps.com](https://make.powerapps.com/).
2. Verifique se você está usando o ambiente no qual ativou a gravação dupla.
3. Na guia **Criar**, role para baixo até a seção **Iniciar do modelo** e selecione o modelo denominado **Portal do Cliente**.
4. Siga as instruções na tela.

Após a conclusão do provisionamento, você poderá acessar o portal do cliente na seção **Seus aplicativos** da página **Inicial**.

> [!NOTE]
> Se a solução de gravação dupla não estiver instalada no ambiente no qual estiver trabalhando, você receberá uma mensagem de erro e o portal do cliente não será provisionado.

## <a name="update-the-customer-portal"></a>Atualize o portal do cliente

Mais funcionalidades poderão ser adicionadas ao portal do cliente posteriormente. As alterações que a Microsoft fizer nos componentes da solução subjacente aparecerão automaticamente no seu ambiente. No entanto, o site provisionado no seu ambiente não refletirá automaticamente as alterações feitas nos dados de configuração. Será necessário aplicar manualmente essas alterações obtendo o código do novo modelo e mesclando-o com o site provisionado.

## <a name="additional-resources"></a>Recursos adicionais

Para saber como você pode configurar e personalizar o portal do cliente, comece analisando a seguinte documentação para as tecnologias subjacentes:

- [Documentação de portais do Power Apps](https://docs.microsoft.com/powerapps/maker/portals/overview)
- [Documentação da gravação dupla](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md)

Para gerenciar com eficiência seus portais, você deve compreender os portais do Power Apps e o ciclo de vida do Microsoft Dataverse. Para obter mais informações, consulte os seguintes recursos:

- [Sobre o ciclo de vida do portal](https://docs.microsoft.com/powerapps/maker/portals/admin/portal-lifecycle)
- [Atualizar um portal](https://docs.microsoft.com/powerapps/maker/portals/admin/upgrade-portal)
- [Migrar configuração do portal](https://docs.microsoft.com/powerapps/maker/portals/admin/migrate-portal-configuration)
- [Gerenciamento do ciclo de vida da solução: Dynamics 365 para aplicativos do Customer Engagement](https://www.microsoft.com/download/details.aspx?id=57777)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]