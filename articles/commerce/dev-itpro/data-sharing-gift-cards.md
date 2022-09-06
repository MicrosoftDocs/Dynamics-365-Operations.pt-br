---
title: Compartilhamento de dados entre empresas para cartões-presente
description: Este artigo descreve como configurar o Microsoft Dynamics 365 Commerce para usar a funcionalidade de compartilhamento de dados do Dynamics 365 Finance nas áreas de dados para sincronizar dados do cartão-presente.
author: BrianShook
ms.date: 08/26/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.custom: 141393
ms.assetid: e23e944c-15de-459d-bcc5-ea03615ebf4c
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2022-06-20
ms.openlocfilehash: b56890b546c3cd74b75cf447e62495733ea8d288
ms.sourcegitcommit: 09d4805aea6d148de47c8ca38d8244bbce9786ce
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387060"
---
# <a name="cross-company-data-sharing-for-gift-cards"></a>Compartilhamento de dados entre empresas para cartões-presente

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Este artigo descreve como configurar o Microsoft Dynamics 365 Commerce, de forma que ele use a funcionalidade de compartilhamento de dados do Dynamics 365 Finance para sincronizar dados do cartão-presente. A funcionalidade de compartilhamento de registros de dados pode então ser usada para compartilhar dados interempresariais entre duas áreas de dados. Dessa forma, a tabela de brindes internos do Commerce pode compartilhar dados entre duas entidades da empresa. Para obter mais informações sobre o compartilhamento de dados interempresarial do Dynamics 365 Finance, consulte [Compartilhamento de dados interempresarial](/dynamics365/fin-ops-core/dev-itpro/sysadmin/cross-company-data-sharing).

## <a name="key-terms"></a>Condições principais

| Termo | Descrição |
|---|---|
| Empresa | A entidade legal no ambiente do Dynamics 365 Finance. |
| Cartão-presente | O produto do cartão-presente interno do Dynamics 365 Commerce. |

## <a name="prerequisites"></a>Pré-requisitos

Os usuários devem configurar seu ambiente para compartilhamento de dados interempresarial, conforme descrito em [Compartilhamento de dados interempresarial](/dynamics365/fin-ops-core/dev-itpro/sysadmin/cross-company-data-sharing).

**RetailGiftCardTable** deve ter o campo **DataSharingType** definido como **Duplicado** para habilitar o DRS (compartilhamento de registro duplicado) para a tabela de cartão-presente. Para obter mais informações, consulte [Compartilhamento de dados interempresarial para desenvolvedores](/dynamics365/fin-ops-core/dev-itpro/sysadmin/drs-srs-dev).

## <a name="configure-cross-company-data-sharing-for-gift-cards"></a>Configurar compartilhamento de dados interempresarial para cartões-presente

Para configurar compartilhamento de dados interempresarial para cartões-presente, siga estas etapas.

1. No Commerce headquarters, vá para **Administração do sistema \> Configuração \> Configurar o compartilhamento de dados entre empresas**.
1. No Painel de Ações, selecione **Novo** para adicionar um registro de compartilhamento de dados.
1. No campo **Nome** insira um nome para o registro de compartilhamento de dados (por exemplo, **Cartões-Presente**).
1. Na seção **Tabelas e campos a serem compartilhados**, selecione **Adicionar**.
1. Na caixa de diálogo **Compartilhar nova tabela** no campo **Nome da tabela**, insira **RETAILGIFTCARDTABLE** (a tabela para cartões-presente de varejo). O campo **Etiqueta da tabela** deve ser automaticamente definido como **Tabela de cartões-presente**.
1. Verifique se as caixas de seleção **Salvar dados por empresa**, **Tem índice exclusivo** e **Ainda não compartilhado** estão todas selecionadas. A seleção dessas caixas de seleção dispara validações relacionadas à funcionalidade de compartilhamento de dados.
1. Selecionar **Adicionar tabela**. O registro **Tabela de cartões-presente (RetailGiftCardTable)** agora deve aparecer em **Tabelas e campos a serem compartilhados**. Selecione o símbolo de circunflexo (^) para exibir todos os campos de tabela associados automaticamente à tabela para compartilhamento.
1. Na seção **Empresas que compartilham os registros nestas tabelas**, selecione **Adicionar** para adicionar uma empresa com a qual compartilhar os dados.
1. Na linha em **Empresa**, selecione uma empresa na lista suspensa.
1. No campo **Nome**, insira o nome da empresa.
1. Repita as etapas 8 a 10 para adicionar mais linhas da empresa.
1. Quando terminar de adicionar linhas de empresa, no Painel de Ações, selecione **Habilitar**.
1. Você receberá uma mensagem de aviso afirmando "É recomendável executar essa ação somente fora do horário comercial. Todas as operações de transação simultâneas falharão para as tabelas na política. Deseja continuar?" Selecione **Sim** para concordar.
1. Você receberá uma mensagem de aviso que informa, "Deseja copiar todos os dados existentes entre todas as empresas compartilhadas agora?" Selecione **Sim** para concordar.

Depois de concordar com as duas mensagens, as tabelas começarão a copiar dados pelas empresas configuradas. Os saldos que ocorrerem em um cartão-presente da empresa ficarão visíveis para a outra empresa.

## <a name="additional-resources"></a>Recursos adicionais

[Perguntas frequentes sobre pagamentos](payments-retail.md)

[Módulo de finalização da compra](../add-checkout-module.md)

[Módulo de pagamento](../payment-module.md)
