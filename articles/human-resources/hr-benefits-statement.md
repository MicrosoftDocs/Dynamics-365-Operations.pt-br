---
title: Demonstrativo de benefícios
description: O relatório Demonstrativo de benefícios explica os benefícios em que um funcionário está inscrito.
author: twheeloc
ms.date: 09/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: a12649cd0604fb6acd58420fdafb5b560fcc10cf
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8688222"
---
# <a name="benefit-statement"></a>Demonstrativo de benefícios


[!INCLUDE [PEAP](../includes/peap-2.md)]

O relatório **Demonstrativo de benefícios** fornece um demonstrativo dos benefícios nos quais um funcionário está registrado. O relatório pode ser acessado por um funcionário de forma direta ou pelo administrador do benefício. O **Demonstrativo de benefícios** fornece uma lista das vantagens registradas do funcionário, opções de cobertura, custos e quaisquer dependentes ou beneficiários registrados. O demonstrativo pode ser impresso para um único trabalhador ou vários trabalhadores.

> [!NOTE]
O recurso **Demonstrativo de benefícios** deve estar habilitado no espaço de trabalho **Gerenciamento de recursos**. Para isso, o recurso **Gerenciamento de benefícios** deverá estar habilitado no Gerenciamento de recursos. 


## <a name="importing-the-benefit-statement"></a>Importação do Demonstrativo de benefícios 

Você deverá importar o **Demonstrativo de benefícios** usando a configuração de relatório antes que o **Demonstrativo de benefícios** esteja disponível. Para fazer isso, conclua as seguintes etapas:

1.  Acesse o espaço de trabalho **Administração do Sistema**.

2.  Selecione o bloco **Relatório Eletrônico**.

3.  Acesse **Provedores de configuração** e selecione **Repositórios**.

  ![Seleção de repositórios.](https://user-images.githubusercontent.com/26801678/134203290-7faf7245-ed08-44e9-95a1-a7ba278c42c6.png)

4.  Selecione **Recursos de RH** na lista e, em seguida, selecione **Abrir**.

    ![Repositórios de configuração.](https://user-images.githubusercontent.com/26801678/134203619-b3fd087d-1fe9-45ef-a588-1afedfe38dfd.png)

5.  Selecione o **modelo Demonstrativo de benefícios** no painel esquerdo e expanda-o para que o **Formato do demonstrativo de benefícios** seja exibido.

6.  Selecione **Formato do demonstrativo de benefícios** no painel esquerdo.

7.  No lado direito da tela, haverá uma Guia Rápida **Versões**. Selecione **Importar**.

    ![Guia Rápida Versões.](https://user-images.githubusercontent.com/26801678/134203763-f12ef549-e326-400d-ac69-b25fc94af47b.png)

## <a name="generate-the-benefit-statement-as-a-pdf-file"></a>Gerar o Demonstrativo de benefícios como um arquivo PDF

Por padrão, o **Demonstrativo de benefícios** será impresso como um documento do Microsoft Word. Para imprimir em um formato PDF, você precisará configurar a opção PDF no **Destino do relatório eletrônico**. 

1. Para fazer isso, acesse **Espaço de trabalho Administração do sistema** > **Relatório eletrônico** > **Links relacionados** > **Destino do relatório eletrônico**.

1.  Selecione **Novo**.

2.  No campo **Referência**, selecione **Formato do demonstrativo de benefícios**.

3.  Na Guia Rápida **Destino do arquivo**, selecione **Novo**.

4.  No campo **Nome**, insira **PDF do Demonstrativo de Benefícios**.

5.  No campo **Nome do componente de arquivo**, selecione **Demonstrativo de benefícios**.

6.  Marque a caixa de seleção **Converter em PDF**.

7.  Selecione **Configurações** do item de menu. 

    ![Destino do arquivo.](https://user-images.githubusercontent.com/26801678/134203881-a3f1ebc3-d816-485d-a53b-026cc29cae64.png)

8.  Selecione a Guia Rápida **Arquivo** e, em seguida, selecione **Habilitado**.

9.  Selecione **OK**.
   
> [!NOTE]
> O recurso de gerenciamento de benefícios está em um estado de Versão preliminar. Há um problema conhecido ao usar a configuração de destino de email no relatório **Destino de relatório eletrônico**. Talvez você receba uma mensagem de erro e o email não será enviado.

O **Demonstrativo de benefícios** pode ser gerado das seguintes páginas:

-   **Espaço de trabalho Gerenciamento de benefícios** > **Links** > **Relatórios** > **Demonstrativo de benefícios**

-   **Funcionários (formulário herdado)** > **Guia Informações pessoais** > **Demonstrativo de benefícios**

-   **Entrada simplificada de funcionários** > **Relatórios de benefícios** > **Demonstrativo de benefícios**

-   **Autoatendimento para funcionários** > **Benefícios** > **Exibir Demonstrativo de benefícios**

> [!NOTE]
>  O acesso ao **Demonstrativo de benefícios** em **Autoatendimento para funcionários** é controlado pelo privilégio **Exibir demonstrativo de benefícios**. Isso fica sob a obrigação **Benefícios de Autoatendimento para Funcionários**. Esse privilégio é concedido a funcionários por padrão.

## <a name="report-contents"></a>Conteúdo do relatório

O **Demonstrativo de benefícios** imprimirá as seleções de plano confirmado do funcionário, inclusive quaisquer planos renunciados. A imagem a seguir mostra um exemplo desse relatório. 

![Relatório Demonstrativo de benefícios.](https://user-images.githubusercontent.com/26801678/134204058-61baa318-fede-4795-a256-acdf3217f9f9.png)

O relatório exibirá **Plano**, **Opção de cobertura**, **Custo do funcionário** e **Custo do empregador**. O relatório também listará os dependentes cobertos. Se o plano tiver os beneficiários associados a ele, os beneficiários e a prioridade de distribuição e a porcentagem serão exibidos.

O relatório **Demonstrativo de benefícios** pode ser impresso para vários funcionários ao mesmo tempo usando a Guia Rápida **Registros a serem incluídos** na página **Demonstrativo de benefícios**.
