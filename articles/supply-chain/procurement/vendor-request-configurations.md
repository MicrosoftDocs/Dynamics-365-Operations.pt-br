---
title: Configurações de solicitação de fornecedor
description: Este artigo descreve os campos que precisam ser preenchidos em uma nova solicitação do fornecedor.
author: GalynaFedorova
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendProspectiveVendorRegistrationConfig
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 0f583caaaf4909918fafc0e8ef08490e25057561
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8890847"
---
# <a name="vendor-request-configurations"></a>Configurações de solicitação de fornecedor
[!include [banner](../includes/banner.md)]

Para concluir uma solicitação do fornecedor, uma pessoa de contato do fornecedor deve concluir o assistente de registro de fornecedor em potencial.

No formulário **Configurações da solicitação do fornecedor**, você pode criar os perfis que especificam campos obrigatórios e campos visíveis em assistente de registro de fornecedor potencial.

O assistente de registro de fornecedor começará a perguntar para o usuário do fornecedor potencial em qual país/região o fornecedor está fazendo negócios. Essas informações determinam a configuração aplicável. Se nenhuma configuração específica for definida para um país/região, a configuração padrão será usada.

### <a name="set-up-a-vendor-request-configuration"></a>Definição de uma configuração de solicitação de fornecedor

Por padrão, há uma configuração de fornecedor disponível no formulário de configurações de solicitação do Fornecedor.

Não é possível selecionar país/regiões para a configuração padrão, assim a seção **Países/regiões** não pode ser alterada.

1. Clique em **Compras** > **Configuração** > **Fornecedores** e depois em **Configurações de solicitação de fornecedor**.
2. Clique na guia **Campos** para definir o status dos campos listados.
3. Oculto (Não visível)
4. Exibido (Visível, mas não obrigatório)
5. Obrigatório (Visível e obrigatório)
6. Clique na guia **Conteúdo** para especificar se o texto está prestes a ser mostrado no assistente e se há uma confirmação de que o usuário do fornecedor potencial deve aceitar isso, antes de se mover para a próxima etapa no assistente. A confirmação será solicitada para os termos e as condições que o usuário deve aceitar para continuar.

Você também pode inserir uma mensagem de confirmação que será exibida quando o assistente for finalizado, e poderá adicionar um ou mais questionários.

### <a name="create-a-vendor-configuration-for-a-specific-countryregion"></a>Crie uma configuração de fornecedor para um país/região específicos
1.  Clique em **Compras** > **Configuração** > **Fornecedores** e depois em **Configurações de solicitação de fornecedor**.
2.  Clique em **Novo** para criar uma nova configuração, e fornecer um nome para a configuração.
3.  Clique em **Salvar**.
4.  Abra a guia **País/regiões** para selecionar o país/região em que a configuração será usada.
5.  Conclua a configuração seguindo as diretrizes para a configuração padrão.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]