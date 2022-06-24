---
title: Integrar o Customer Voice às páginas do site de comércio eletrônico
description: Este artigo descreve como integrar o Microsoft Dynamics 365 Customer Voice em páginas de site de comércio eletrônico do Dynamics 365 Commerce.
author: samjarawan
ms.date: 05/17/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2019-10-31
ms.openlocfilehash: c8c67ecf4950c92fc91c8d119e06e5e8afff0ddf
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8850321"
---
# <a name="integrate-customer-voice-into-e-commerce-site-pages"></a>Integrar o Customer Voice às páginas do site de comércio eletrônico

[!include [banner](../includes/banner.md)]

Este artigo descreve como integrar o Microsoft Dynamics 365 Customer Voice em páginas de site de comércio eletrônico do Dynamics 365 Commerce.

Você pode integrar o [Customer Voice](https://dynamics.microsoft.com/customer-voice/overview/) no site de comércio eletrônico para coletar, analisar e rastrear comentários de clientes em tempo real. Para iniciar a integração, você deve criar uma conta e selecionar um modelo de projeto do Customer Voice para o tipo de comentários que deseja coletar.

## <a name="integrate-the-customer-voice-service"></a>Integrar o serviço do Customer Voice

Para criar uma conta do Customer Voice, vá para [Customer Voice](https://dynamics.microsoft.com/customer-voice/overview/) e siga os prompts.

Após criar uma conta do Customer Voice e entrar, a próxima etapa será selecionar um modelo de projeto para o tipo de comentário que você deseja coletar.

Para selecionar um modelo de projeto do Customer Voice, siga estas etapas.

1. Vá para a [página de modelo de projeto de voz do Customer Voice](https://customervoice.microsoft.com/Pages/ProjectPage.aspx).
1. Selecione **Introdução**.
1. Selecione o modelo de projeto do tipo de comentários a ser coletado e, depois, selecione **Avançar**.
1. Na guia **Enviar**, em **Escolher um formato de inserção**, selecione um formato de inserção. O campo **Código inserido** mostra o código que deve ser inserido no construtor de sites do Commerce.

Os exemplos neste artigo usam o modelo de projeto de **Pesquisa de cliente periódica** e o formato de inserção de **Botão**.

A ilustração de exemplo a seguir mostra a página de modelo de projeto de **Pesquisa de cliente periódica**, na qual a opção do formato de inserção do **Botão** é selecionada, e o código de inserção dessa opção aparece no campo **Código inserido**. Três ações separadas são necessárias para inserir o código fornecido nas páginas do seu site, conforme descrito nas seções a seguir.

![Página de Pesquisa de cliente periódica do Customer Voice com a opção Botão selecionada.](media/customer-voice-integration-1.png)

### <a name="embed-the-external-script-url"></a>Inserir a URL do script externo

Em todas as páginas do site que devem ter uma pesquisa do Customer Voice, você deve inserir a URL do script externo que o Customer Voice forneceu no código inserido. A melhor forma de inserir o script em páginas de vários sites é criar um fragmento no construtor de sites que contém a URL do script externo e, depois, adicionar o fragmento aos modelos de página apropriados. Após publicar um modelo atualizado, o código de script externo inserido será semelhante ao exemplo a seguir em páginas de sites afetados.

```html
<script src=https://mfpembedcdnmsit.azureedge.net/mfpembedcontmsit/Embed.js type="text/javascript"></script>
```

Para obter informações sobre fragmentos, consulte [Trabalhar com fragmentos](work-with-fragments.md).

> [!NOTE]
> Você só precisa adicionar a URL ao fragmento. O módulo de script externo adicionará o outro código de script.

Para inserir a URL do script externo a um fragmento, siga estas etapas.

1. No construtor de sites, crie um fragmento baseado no [Módulo de script externo](script-module.md).
1. No novo fragmento, selecione o slot **Script externo padrão**.
1. No painel de propriedades **Script externo padrão**, no campo **Origem do script**, insira a URL do script externo, conforme mostrado na ilustração de exemplo a seguir.

    ![URL do script externo no campo Origem do script do novo fragmento.](media/customer-voice-integration-2.png)

1. Selecione **Salvar** e **Finalizar edição**.
1. Selecione **Publicar** para publicar o fragmento.

O novo fragmento contendo o bloco de script externo inserido agora está pronto para ser adicionado ao modelo de página apropriado.

### <a name="embed-the-external-style-sheet-code"></a>Inserir o código de folha de estilos externo

Depois, em todas as páginas do site que devem ter uma pesquisa do Customer Voice, você deve inserir o código de folha de estilos que o Customer Voice forneceu no código inserido. Como na seção anterior, a melhor forma de inserir o código de folha de estilos externo em páginas de vários sites é criar um fragmento no construtor de sites que contém o código de folha de estilos e, depois, adicionar o fragmento aos modelos de página apropriados. O código de folha de estilos externo inserido será semelhante ao exemplo de código a seguir.

```typescript
<link rel="stylesheet" type="text/css" href=https://mfpembedcdnmsit.azureedge.net/mfpembedcontmsit/Embed.css />
```

Para inserir o código de folha de estilos externo em um fragmento, siga estas etapas.

1. No construtor de sites, crie um fragmento baseado no [Módulo Meta tags](metatags-module.md).
1. No fragmento, selecione o slot **Meta tags padrão**.
1. No painel de propriedades **Meta tags padrão**, no campo **Meta tags**, insira o código de folha de estilos, conforme mostrado na ilustração de exemplo a seguir.

    ![Código de folha de estilos externo no campo Meta tags para o novo fragmento.](media/customer-voice-integration-3.png)

1. Selecione **Salvar** e **Finalizar edição**.
1. Selecione **Publicar** para publicar o fragmento.

O novo fragmento contendo o código da folha de estilos externo inserido agora está pronto para ser adicionado ao modelo de página apropriado.

### <a name="embed-the-inline-script-code"></a>Inserir o código de script em linha 

Em todas as páginas do site que devem ter uma pesquisa do Customer Voice, você deve inserir o código de script em linha que o Customer Voice forneceu no código inserido. Como nas seções anteriores, a melhor forma de inserir o código de script em linha em páginas de vários sites é criar um fragmento no construtor de sites contendo o código de script em linha e, depois, adicionar o fragmento aos modelos de página apropriados.

No exemplo a seguir de código de script em linha, **SURVEY\_KEY** é um espaço reservado. O valor de **SURVEY\_KEY** deve corresponder à chave da pesquisa real que o Customer Voice forneceu no código de inserção. A última linha chama o código para processar o botão de pesquisa após um segundo, a fim de garantir que os scripts tenham tempo suficiente para serem carregados. Dependendo da pesquisa selecionada, talvez você também precise adicionar ou atualizar outros metadados, como o nome da empresa.

```html
function renderSurveyButton() {
    var se = new SurveyEmbed("SURVEY_KEY","https://customervoice.microsoft.com/","https://mfpembedcdnmsit.azureedge.net/mfpembedcontmsit/","true");

    var context = {
        "First Name":"",
        "Last Name": "",
        "locale": "en-us",
        "companyname": "Adventure Works"
    };
    se.renderButton(context);
}

setTimeout(renderSurveyButton, 4000);
```

Para inserir o código de script em linha em um fragmento, siga estas etapas.

1. No construtor de sites, crie um fragmento baseado no [módulo Script em linha](script-module.md).
1. No fragmento, selecione o slot **Script em linha padrão**.
1. No painel de propriedades **Script em linha padrão**, no campo **Script em linha**, insira o código de script em linha, conforme mostrado na ilustração de exemplo a seguir.

    ![Código de script em linha no campo Script em linha do novo fragmento.](media/customer-voice-integration-4.png)

1. Selecione **Salvar** e **Finalizar edição**.
1. Selecione **Publicar** para publicar o fragmento.

O novo fragmento contendo o código de script em linha inserido agora está pronto para ser adicionado ao modelo de página apropriado.

## <a name="add-fragments-to-a-template"></a>Adicionar fragmentos a um modelo

Ao terminar de criar os fragmentos contendo o código inserido do Customer Voice, adicione-os aos modelos de página que estão associados às páginas do site em que você deseja usá-los. Na ilustração do exemplo a seguir, os três fragmentos de exemplo foram adicionados a um modelo PDP (página de detalhes do produto).

![Exemplos de fragmentos adicionados a um modelo PDP.](media/customer-voice-integration-5.png)

Depois que o modelo atualizado for publicado, a pesquisa do Customer Voice aparecerá em todas as páginas controladas pelo modelo.

Para obter informações sobre modelos, consulte [Trabalhar com modelos](work-with-templates.md).

## <a name="configure-content-security-policy"></a>Configurar a política de segurança de conteúdo

Por padrão, a CSP (política de segurança de conteúdo) não permite chamadas para outros serviços, a menos que uma configuração adicional seja realizada. Portanto, depois de publicar os modelos atualizados, é provável que a pesquisa não seja carregada nas páginas relevantes do site. Para exibir os erros relacionados à CSP, abra as ferramentas de desenvolvedor do navegador da Web (F12) e vá para uma página com a pesquisa. Os erros relacionados à CSP aparecerão na saída do console.

Para configurar a CSP na construtor de sites para corrigir os erros, siga estas etapas.

1. Acesse **Configurações do site \> Extensões**.
1. Na guia **Política de segurança de conteúdo**, adicione `https://customervoice.microsoft.com/` à diretiva **child-src**.
1. Adicione `https://customervoice.microsoft.com/` à diretiva **frame-src**.
1. Adicione `https://mfpembedcdnmsit.azureedge.net` e **.azureedge.net** à diretiva **img-src**.

Para obter mais informações, consulte [Política de segurança de conteúdo](manage-csp.md).

## <a name="additional-resources"></a>Recursos adicionais

[Módulo de script externo](script-module.md)

[Módulo de metamarcas](metatags-module.md)

[Módulo de script em linha](script-module.md)

[Política de segurança de conteúdo](manage-csp.md)

[Trabalhar com fragmentos](work-with-fragments.md)

[Trabalhar com modelos](work-with-templates.md)
