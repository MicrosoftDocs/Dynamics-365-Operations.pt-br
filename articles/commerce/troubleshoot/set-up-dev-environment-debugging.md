---
title: Configurar um ambiente de desenvolvimento de comércio eletrônico para depurar em uma máquina virtual do servidor de varejo de nível 1
description: Este artigo explica como configurar um ambiente de desenvolvimento de comércio eletrônico para depurar em uma máquina virtual (VM) do servidor de varejo de nível 1.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: 64e03c742f7095e2e485f32ad534f2a755ddd062
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277870"
---
# <a name="set-up-an-e-commerce-development-environment-to-debug-against-a-tier-1-retail-server-virtual-machine"></a>Configurar um ambiente de desenvolvimento de comércio eletrônico para depurar em uma máquina virtual do servidor de varejo de nível 1

[!include [banner](../../includes/banner.md)]

Este artigo explica como configurar um ambiente de desenvolvimento de comércio eletrônico para depurar em uma máquina virtual (VM) do servidor de varejo de nível 1.

## <a name="description"></a>descrição

Os ambientes da camada 1 do Microsoft Dynamics 365 Commerce geralmente são implantados para desenvolvimento de extensões de Commerce Runtime (CRT) e ponto de venda (PDV). São ambientes autônomos. Devido à natureza do software como um serviço (SaaS) da arquitetura, eles não incluem componentes de comércio eletrônico.

Em algumas situações, talvez você queira testar chamadas para extensões em um ambiente de nível 1, de forma que possa depurar extensões de componentes de comércio eletrônico. Para obter instruções gerais, consulte [Depuração em relação a um ambiente de desenvolvimento do Commerce de Camada 1](../e-commerce-extensibility/debug-tier-1.md).

Quando você depura um ambiente de nível 1, porque o site agora está chamando um servidor de varejo diferente, as chamadas entre servidores podem causar vários erros relacionados à política de segurança de conteúdo.

A ilustração a seguir mostra um exemplo de um erro que pode ocorrer quando uma variante está selecionada em uma página de detalhes do produto.

![Erro quando uma grade é selecionada em uma página de detalhes do produto.](media/unhandled-rejection-error.jpg)

A ilustração a seguir mostra um exemplo de erro semelhante em ferramentas de depuração de um navegador (Ferramentas para Desenvolvedores F12). A mensagem de erro menciona violação da diretiva da política de segurança de conteúdo.

![Erro nas ferramentas do depurador.](media/debugger-tools-error.JPG)

## <a name="resolution"></a>Resolução

### <a name="disable-the-content-security-policy-for-the-site-in-commerce-site-builder"></a>Desabilitar a diretiva de segurança de conteúdo do site no criador de sites do Commerce

1. Selecione o site no qual você está trabalhando.
1. Selecione **Configurações** e, em seguida, selecione **Extensões**.
1. Na guia **Política de segurança de conteúdo**, selecione **Desabilitar política de segurança de conteúdo**.
1. Selecione **Salvar e publicar**.

> [!NOTE]
> A entrada de empresa a consumidor (B2C) não funcionará em um ambiente de desenvolvimento local. No entanto, você pode usar finalizações de compra do convidado ou compilar simulações de página para simular uma entrada do usuário, conforme necessário.

## <a name="additional-resources"></a>Recursos adicionais

[Comece com o desenvolvimento de extensibilidade online de comércio eletrônico](../e-commerce-extensibility/sdk-getting-started.md)

[Gerenciar a CSP (política de segurança de conteúdo) no site de comércio eletrônico](../manage-csp.md)
