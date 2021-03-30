---
title: Layouts de tela de dados de demonstração no Modern POS (MPOS) e no PDV em Nuvem
description: Este tópico fornece informações sobre os layouts de tela que são incluídos no conjunto de dados de demonstração das experiências do ponto de venda (POS) no Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 10/05/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTillLayout
audience: Application user
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2017-10-05
ms.dyn365.ops.version: Retail April 2017 update
ms.openlocfilehash: 5e75210e77d1187f482d716f795ec0155553cb3f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5213616"
---
# <a name="demo-data-screen-layouts-in-modern-pos-mpos-and-cloud-pos"></a>Layouts de tela de dados de demonstração no Modern POS (MPOS) e no PDV em Nuvem

[!include [banner](includes/banner.md)]

Este tópico fornece informações sobre os layouts de tela que são incluídos no conjunto de dados de demonstração das experiências do ponto de venda (POS) no Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

Os layouts de tela de exemplo incluídos nos dados de demonstração do Commerce fornecem conteúdo que é otimizado para vários segmentos de varejo, funções de trabalho de lojas e dispositivos. Um único layout pode conter vários tamanhos de layout e combinações de grades de botões, para garantir a cobertura à medida que trabalhadores de lojas se movem entre estações e dispositivos. Este tópico destaca as diferenças entre os layouts, as operações oferecidas e as experiências em geral que eles propiciam.

![Layouts de dados de demonstração entre dispositivos](../commerce/media/demo-screen-layouts-fig-1-1.png)

## <a name="anatomy-of-a-screen-layout-id"></a>Anatomia da ID do layout de uma tela

Para encontrar layouts de tela, vá para **Varejo e Comércio** \> **Configuração de canal** \> **Configuração do PDV** \> **PDV** \> **Layouts de tela**.

![Página de layouts de tela](../commerce/media/demo-screen-layouts-fig-2-1.png)

As IDs do layout de tela podem ter no máximo 10 caracteres. A ID é uma cadeia de caracteres que consiste em três informações, nesta ordem:

1. Empresa
2. Versão do layout
3. Persona

### <a name="company"></a>Empresa

| Carta | Empresa         |
|--------|-----------------|
| A      | Adventure Works |
| F      | Fabrikam        |
| C      | Contoso         |

### <a name="layout-version"></a>Versão do layout

| Número da Versão | descrição                                                                                |
|----------------|--------------------------------------------------------------------------------------------|
| 3              | A versão base que dá suporte a vários tamanhos de tela para vários dispositivos e taxas de proporção |
| 3.1            | A versão base que tem suporte adicional para o painel **Produtos recomendados**        |
| 4              | A versão estendida do layout atualizado da Fabrikam estendida                                  |

### <a name="persona"></a>Persona

| Abreviação | Persona       | Conteúdo |
|--------------|---------------|----------|
| CSH          | Caixa       | Os layouts de caixa incluem todas as operações relativas a transações, como ordens de cliente, devoluções, descontos, cancelamentos e cartões-presente. Esses layouts também incluem tarefas diárias para gerenciamento de estoque, como verificações de preço, pesquisas de estoque e contagens de estoque. O gerenciamento básico de turno também é fornecido para valores iniciais, turnos suspensos e relógio de ponto. |
| MGR          | Gerente da loja | Os layouts de gerente de loja incluem todas as operações relativas à transação que se encontram nos layouts de caixa, mas também incluem substituições de imposto. Esses layouts também incluem tarefas diárias para gerenciamento de estoque, como verificações de preço, pesquisas de estoque e contagens de estoque. O gerenciamento de turnos é fornecido para iniciar, suspender e fechar turnos. Layouts também incluem operações de sacador para entradas, remoções, declarações de meios de pagamento, além de depósitos em cofre e depósitos bancários. Finalmente, esses layouts incluem acesso a relatórios de desempenho, e habilitam a impressão de relatórios X e Z. |
| STK          | Almoxarife   | Layouts de almoxarife são otimizados para o gerenciamento de estoque. Eles incluem o acesso às tarefas diárias para verificações de preço, pesquisas de estoque, separação e recebimento, contagens de estoque e desmontagem de kit. Esses layouts também fornecem operações básicas de turnos para relógio de ponto e suspensão de turnos. Embora esses layouts se destinem principalmente a tarefas de back office, almoxarifes têm as mesmas operações que caixas de telas de transação. |

### <a name="example-layout"></a>Layout de exemplo

Aqui está um exemplo de uma ID do layout da tela da empresa Fabrikam, versão 4 do layout, e persona do gerente de loja:

F4MGR

A ilustração a seguir mostra um exemplo da tela de boas-vindas de um gerente de loja da Fabrikam.

![Tela de boas-vindas do gerente de loja da Fabrikam](../commerce/media/demo-screen-layouts-fig-2-2.png)

## <a name="layout-sizes"></a>Tamanhos de layout

### <a name="full-vs-compact-layouts"></a>Layouts completos vs compactos

Um layout de tela pode ter configurações para dispositivos completos e compactos. Então, um usuário pode ser atribuído a um único layout de tela que funcionará em vários tamanhos e fatores forma na loja.

- **Modern POS - Completo** - Layouts completos costumam ser melhor usados para telas maiores, como monitores de desktop ou tablets. Os usuários podem selecionar elementos de interface de usuário incluídos pelo layout, especificar o tamanho e o posicionamento desses elementos, e configurar as propriedades detalhadas. Os layouts completos suportam configurações de retrato e de paisagem.
- **Modern POS - Compacto** - Layouts compactos costumam ser melhor usados para telefones ou tablets pequenos. Possibilidades de design são limitadas para dispositivos compactos. Os usuários podem configurar as colunas e campos para os painéis de recebimento e de totais.

### <a name="screen-resolutions-that-are-provided"></a>Resoluções de tela que são fornecidas

A tabela a seguir mostra os tamanhos de layout fornecidos para resoluções de tela típicas.

| Tipo de layout | Resolução | Taxa de proporção | Exibição de destino          |
|-------------|------------|--------------|-------------------------|
| Compactar\*   | 480 × 853  | 16:9         | Telefones                  |
| Completo        | 1024 × 768 | 4:3          | Tablets                 |
| Completo\*      | 1280 × 720 | 16:9         | Tablets                 |
| Completo        | 1366 × 768 | 16:9         | Tablets, telas maiores |
| Completo        | 1440 × 960 | 3:2          | Tablets, telas maiores |
| Completo\*      | 1536 × 864 | 16:9         | Tablets, telas maiores |

\* Esses tamanhos de layout adicionais estão disponíveis apenas nos layouts da Adventure Works e da Fabrikam.

> [!TIP]
> O PDV seleciona automaticamente tamanhos do layout, com base no próximo tamanho disponível para resolução de tela da janela do aplicativo atual. Para localizar a ID do layout da tela e a resolução de layout que estão sendo usadas no momento, no Modern POS (MPOS) ou no Retail Cloud POS (CPOS), abra a página **Configurações** e verifique a seção **Informações da sessão**. Você também pode consultar a resolução da janela real no quadro do aplicativo ou navegador atual. Quando tiver essas informações, você poderá localizar a fonte do conteúdo do layout, acessando **Configuração de canal** \> **Configuração do PDV** \> **PDV** \> **Layouts da tela**.

![Layouts da tela e resoluções/tamanhos de layout no Commerce e no PDV](../commerce/media/demo-screen-layouts-fig-3-1.png)

## <a name="companies-and-brands"></a>Empresas e marcas

Cada empresa fictícia é direcionada a um segmento de varejo diferente, e inclui os catálogos de produtos que são ajustados para o mercado da empresa. Cada empresa tem uma marca visual exclusiva que acompanha seus produtos. Elementos de marca incluem cor de destaque, tema escuro ou claro, e fotografias que fornecem experiências realistas.

### <a name="company-segment-and-visual-characteristics"></a>Segmento empresarial e características visuais

| Empresa         | Local | Segmento        | Destaque | Tema |
|-----------------|----------|----------------|--------|-------|
| Adventure Works | Seattle  | Mercadorias esportivas | Azul   | Escuro  |
| Fabrikam        | São Francisco  | Moda        | Verde  | Claro |
| Contoso         | Boston   | Eletrônicos    | Vermelho    | Escuro  |

> [!NOTE]
> A Adventure Works e a Fabrikam são duas marcas independentes. A Contoso está disponível, mas nem todos os layouts foram fornecidos.

As ilustrações a seguir mostram exemplos da página de boas-vindas e da página de transação para as três empresas fictícias.

### <a name="adventure-works"></a>Adventure Works

![Página de boas-vindas de dados de demonstração para a Adventure Works](../commerce/media/demo-screen-layouts-fig-4-1a.png)

![Página de transação de dados de demonstração para a Adventure Works](../commerce/media/demo-screen-layouts-fig-4-1b.png)

### <a name="fabrikam"></a>Fabrikam

![Página de boas-vindas de dados de demonstração para a Fabrikam](../commerce/media/demo-screen-layouts-fig-4-2a.png)

![Página de transação de dados de demonstração para a Fabrikam](../commerce/media/demo-screen-layouts-fig-4-2b.png)

### <a name="contoso"></a>Contoso

![Layouts de dados de demonstração da Contoso](../commerce/media/demo-screen-layouts-fig-4-3.png)

## <a name="user-sign-in-matrix"></a>Entrada do usuário na matriz

Os usuários receberam os vários layouts de tela. Usando esta tabela, você deve conseguir acessar qualquer tela. Basta entrar usando uma ID de operador apropriada.

| Empresa         | ID do layout da tela | Persona       | IDs de Operador           |
|-----------------|------------------|---------------|------------------------|
| Adventure Works | A3MGR            | Gerente da loja | 000154, 000137, 000073 |
| Adventure Works | A3CSH            | Caixa       | 000150, 000175, 000165 |
| Adventure Works | A3STK            | Almoxarife   | 000155, 000181, 000152 |
| Fabrikam        | F4MGR            | Gerente da loja | 000160, 000713         |
| Fabrikam        | F3CSH            | Caixa       | 000161, 000113, 000114 |
| Fabrikam        | F3STK            | Almoxarife   | 000164, 000112, 000123 |
| Contoso         | C3MGR            | Gerente da loja | 000100, 000111         |
| Contoso         | C3CSH            | Caixa       | 000110, 000120         |
| Contoso         | Não Aplicável   | Almoxarife   | Não Aplicável         |

> [!TIP]
> Para obter melhores resultados, ative um registro no local de loja correspondente, e defina a empresa como a empresa da persona que você pretende usar ao entrar. Assim, você ajuda a garantir que o perfil visual e as imagens de marcas estejam alinhados na experiência. Por exemplo, se você estiver interessado em ver um layout da Fabrikam para um caixa, ative um registro na loja de Houston.

<!-- Hiding until the content page is available on CustomerSource -->

<!-- ## Reference icons and images -->

<!-- The screen layouts, button grids, and visual profiles were created using images and icons that can be found in **Retail and Commerce \> Channel setup \> POS setup \> POS \> Images**. -->

<!-- ![Images in Dynamics 365 Commerce](../commerce/media/demo-screen-layouts-fig-5-1.png) -->

<!-- Use the [POS Icon and Image Mapping](../commerce/media/POS_Icon_and_Image_Mapping.xlsx) reference spreadsheet to locate operation icons, reference photos, swap logos, or provide new images of your own that can be referenced in custom designs. -->

<!-- END HIDDEN CONTENT -->


[!INCLUDE[footer-include](../includes/footer-banner.md)]