---
title: Configurar e criar formatos de recibo
description: Este artigo descreve como modificar layouts de formulário para controlar como os recibos, as notas fiscais e outros documentos serão impressos. O Dynamics 365 Commerce inclui um designer do layout de formulário que você pode usar para criar e modificar de modo fácil e gráfico diversos tipos de layouts de formulário.
author: rubencdelgado
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailFormLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 57841
ms.assetid: e530dd8e-95e2-4021-90bd-ce1235f9e250
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: ab6b01d6833850af8c04167d94b0a60c7312075c
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3021646"
---
# <a name="set-up-and-design-receipt-formats"></a>Configurar e criar formatos de recibo

[!include [banner](includes/banner.md)]

Este artigo descreve como modificar layouts de formulário para controlar como os recibos, as notas fiscais e outros documentos serão impressos. O Dynamics 365 Commerce inclui um designer do layout de formulário que você pode usar para criar e modificar facilmente vários tipos de layout de formulário

> [!IMPORTANT]
> Você deve configurar layouts de formulário e perfis de recibo para imprimir recibos e outros documentos no Retail Modern POS e no Cloud POS. Você pode incluir vários layouts de formulário em um perfil de recibo. Em seguida, você pode atribuir o perfil de recibo a uma impressora modificando um perfil de hardware.

## <a name="set-up-a-receipt-format"></a>Configurar um formato de recibo

1. Clique em **Retail e Commerce** &gt; **Configuração de canal** &gt; **Configuração do PDV** &gt; **PDV** &gt; **Formatos de recibo**.
2. Na página **Formato de recibo**, clique em **Novo** para criar um novo layout de formulário ou selecione um layout de formulário existente.
3. No campo **Formato de recibo**, insira um identificador para o layout de formulário e selecione o tipo de recibo para o qual esse layout será usado. Você também pode inserir uma descrição e um nome curto para o recibo no campo **Título**.
4. Na Guia Rápida **Geral**, selecione uma opção para definir o comportamento da impressão:

    - **Sempre imprimir** – O recibo é impresso automaticamente, conforme apropriado.
    - **Não imprimir** – O recibo não é impresso.
    - **Avisar usuário** – O usuário será solicitado a imprimir o recibo.
    - **Conforme necessário** – Esta opção é usada apenas para os recibos de presentes. Quando essa opção for selecionada, o usuário poderá imprimir um recibo de presente na página **Alterar** se um recibo de presente for necessário.

## <a name="design-a-receipt-format"></a>Criar um formato de recibo

Use o designer de layout de formulário para criar graficamente o layout do documento do formulário. A página **Designer de formato de recibo** tem três seções: **Cabeçalho**, **Linhas** e **Rodapé**. Alguns tipos de layouts de formulário usam elementos das três seções, enquanto outros tipos usam elementos de apenas uma ou duas seções. Para exibir os elementos que estão disponíveis em cada seção, clique no botão apropriado no painel de navegação no lado esquerdo da página.

1. Clique em **Retail e Commerce** &gt; **Configuração de canal** &gt; **Configuração do PDV** &gt; **PDV** &gt; **Formatos de recibo**.
2. Na página **Formato de recibo**, selecione um layout de formulário e clique em **Designer**.
3. Clique em **Executar** para começar a instalar o host de designer Commerce.
4. Na barra de notificação exibida na parte inferior da janela do Internet Explorer, clique em **Abrir** para começar a instalação do designer de um clique. (A barra de notificação poderá aparecer em um outro local em outros browsers.) O indicador de progresso mostra o progresso do processo de instalação.
5. Ao final da instalação, insira seu nome de usuário e senha do Commerce, e clique em **Entrar** para iniciar o designer.
6. Depois que suas credenciais forem validadas e o designer for iniciado, você poderá começar a criar o formato de recibo ou modificar um formato existente.
7. Para criar os elementos do formulário, selecione a seção **Cabeçalho**, **Linhas** ou **Rodapé** e arraste um elemento dessa seção para o espaço de trabalho. A maioria dos elementos contém variáveis que são preenchidas automaticamente com dados do banco de dados. Outros elementos, como **Texto**, permitem imprimir texto personalizado no recibo.

    > [!NOTE]
    > Você pode especificar por quantas linhas cada seção se estende ajustando o número no canto inferior direito dessa seção. Para facilitar a modificação de uma seção, aumente sua altura arrastando a barra de dimensionamento na parte inferior da seção. A altura da seção no espaço de trabalho não afeta o número de linhas no recibo real.

8. Após arrastar um elemento para o espaço de trabalho, defina as propriedades da parte no painel **Informações do objeto** na parte inferior da página. Especifique uma ou mais das seguintes configurações:

    - **Alinhar** – defina o alinhamento do campo à **Esquerda** ou à **Direita**.
    - **Caractere de preenchimento** – Especifique o caractere de espaço em branco. Por padrão, um espaço em branco é usado, mas você pode inserir qualquer caractere.
    - **Prefixo** – Insira o valor que aparece no início do campo. Essa configuração se aplica apenas à seção **Linhas** do layout.
    - **Caracteres** – Especifique o número máximo de caracteres que o campo poderá conter se o elemento tiver uma variável. Se o texto no campo for maior do que o número de caracteres que você especificar, o texto será truncado para se ajustar ao campo.
    - **Variável** – Esta caixa de seleção será marcada automaticamente se o elemento contiver uma variável e não puder ser personalizado.
    - **Tipo de fonte** – Defina o estilo de fonte como **Normal** ou **Negrito**. As letras em negrito usam duas vezes mais espaço que as letras normais. Portanto, alguns caracteres podem ser truncados.
    - **Tamanho de fonte** – Defina o estilo de fonte como **Normal** ou **Grande**. As letras grandes são duas vezes maiores do que as letras comuns. Portanto, o uso de letras grandes pode levar à sobreposição de texto no recibo.
    - **Excluir** – Clique neste botão para remover o componente selecionado do layout do formulário.

## <a name="assign-receipt-profiles"></a>Atribuir perfis de recibo

Os perfis de recibo são atribuídos diretamente às impressoras por meio do perfil de hardware.

1. Abra o perfil de hardware clicando em **Retail e Commerce** &gt; **Configuração de canal** &gt;**Configuração do PDV** &gt; **Perfis de PDV** &gt; **Perfil de hardware**.
2. Selecione a impressora e, no campo **Perfil de recibo**, atribua o perfil de recibo a ser usado no registro

> [!NOTE]
> Se duas impressoras forem usadas, uma delas poderá ser usada para imprimir recibos térmicos padrão de 40 colunas. A segunda normalmente é usada para imprimir tipos de recibo de página inteira que requerem mais informações. Esses tipos de recibo incluem recibos de ordens de clientes e faturas de clientes.
