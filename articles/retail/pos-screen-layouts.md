---
title: Configurar layouts de tela para PDV
description: "Este tópico fornece informações sobre layouts de tela para experiências com o ponto de venda (PDV) do Microsoft Dynamics 365 for Retail."
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 90573
ms.assetid: a6868f93-02ed-4928-9f6a-3b7383e7e399
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: dd2a42ac824dcf55646594b7cb686401214bb3bc
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="configure-screen-layouts-for-pos"></a>Configurar layouts de tela do PDV

[!include[banner](includes/banner.md)]


Este tópico fornece informações sobre layouts de tela para experiências com o ponto de venda (PDV) do Microsoft Dynamics 365 for Retail.

A interface de usuário do ponto de venda (PDV) do Microsoft Dynamics 365 for Retail pode ser configurada usando uma combinação de perfis visuais e layouts de tela, atribuída a lojas, registros e/ou usuários.

## <a name="visual-profile"></a>Perfil visual
Os perfis visuais são atribuídos aos registros e usados para especificar os elementos visuais que são específicos do registro e compartilhado entre os usuários. Qualquer usuário que entrar no registro terá o mesmo tema, cores e imagens. 

**Número de perfil** - O número de perfil é o identificador único do perfil Visual. 

**Descrição** - A descrição permite que você especifique um nome significativo que ajudará a identificar o perfil correto de sua situação.

**Tema** - Os usuários não podem escolher entre os temas de aplicativo Claro ou Escuro. Essas configurações afetam a fonte e as cores de plano de fundo em todo o aplicativo.

**Cor de destaque** - A cor de destaque é usada em toda a PDV para diferenciar ou destacar determinados elementos visuais como blocos, botões de comando ou hyperlinks. Normalmente, esses elementos são acionáveis.

**Cor do cabeçalho** - A cor do cabeçalho permite que o usuário configure a cor do cabeçalho da página para ser compatível com as necessidades da marca ou varejista. Esse recurso está disponível apenas no Dynamics 365 for Retail, versão 1611.

**Planos de fundo de login** - Os usuários podem especificar uma imagem de plano de fundo para a tela de login. O tamanho do arquivo de imagens de plano de fundo deve ser mantido como o menor possível, pois os arquivos de carregamento e armazenamento grandes podem ter um impacto no comportamento do aplicativo e desempenho.

**Plano de fundo do aplicativo** - O PDV também pode usar uma imagem como um plano de fundo ao longo do aplicativo no lugar da cor sólida do tema. Igual aos planos de fundo de login, é aconselhável manter o tamanho do arquivo o menor possível.

## <a name="screen-layouts"></a>Layouts da tela
A configuração do layout de tela determina as ações, conteúdo e posicionamento dos controles de IU na tela de boas-vindas do PDV e na tela de transação. 

**Tela de boas-vindas**- Na maioria dos casos, a tela de boas-vindas é a página que os usuários verão ao fazer logon pela primeira vez no PDV. A tela de boas-vindas pode ter uma imagem da marca e grades de botão que fornecem acesso às operações do PDV. Normalmente, as operações que não são específicas à transação atual são colocadas aqui. 

**Tela de transação** - A tela de transação é a tela principal no PDV para processar transações de vendas e ordens. A tela de transação pode ser configurada usando o Designer de layout de tela. 

**Tela inicial padrão** - Alguns varejistas preferem que o caixa navegue diretamente para a tela de transação após login. A configuração da tela inicial padrão permite que os usuários a definam para cada layout de tela.

### <a name="assignment"></a>Atribuição

Os layouts de tela podem ser atribuídos à loja, registro ou nível de usuário. A atribuição de usuário sobrepõem a atribuição de registro e loja, e a atribuição de registro sobrepõem à de loja. Em um cenário simples onde todos os usuários usam o mesmo layout independentemente do registro ou da função, o layout da tela pode ser definido apenas na loja. Em alguns casos onde os registros ou usuários precisam de layouts especializados, eles podem ser atribuídos apropriadamente.

### <a name="layout-sizes"></a>Tamanhos de layout

Esse recurso aplica-se apenas ao Dynamics 365 for Retail, versão 1611. Como em muitos casos os layouts de tela podem ser usados por vários tamanhos de tela e resoluções, os usuários podem configurar seu layout e conteúdo para cada um. O aplicativo de PDV escolherá automaticamente o tamanho de layout mais próximo para o dispositivo no momento de início. Um layout de tela pode também conter configurações para dispositivos compactos e completos. Essa configuração permite que um usuário seja atribuído a um único layout de tela que funcionará nos vários tamanhos e fatores de forma dentro da loja. 

**Modern POS - Completo** - Layouts completos são, geralmente, melhor usados para telas maiores como monitores de PC ou tablets. Os usuários podem escolher quais elementos da IU são incluídos, determinar seu tamanho e posicionamento, além de configurar suas propriedades detalhadas. Os layouts completos suportam configurações de retrato e de paisagem. 

**Modern POS - Compacto** - Layouts compactos são, geralmente, melhor usados para telefones ou tablets pequenos. Possibilidades de design são limitadas para dispositivos compactos. Os usuários podem configurar as colunas e campos para recebimento e painéis totais.

### <a name="screen-layout-designer"></a>Designer do layout da tela

Cada tamanho do layout em um layout de tela deve ser configurado usando o designer do layout da tela. O designer permite que os usuários especifiquem e configurem elementos de interface de usuário da tela de transação. O designer do layout de tela usa ClickOnce para baixar, instalar e lançar a versão mais recente do aplicativo toda vez que o usuário o acessar. Confirme a verificação dos requisitos de navegador para uso do ClickOnce, pois alguns navegadores, como o Chrome, precisam de extensões. 

**Teclado numérico** - O Teclado numérico é a entrada de usuário principal na tela de transação de PDV. Pode ser configurado para mostrar o teclado virtual inteiro, que é ideal para telas de toque, ou apenas o campo de entrada, que pode ser usado com um teclado físico. As configurações de teclado numérico estão disponíveis apenas no layout completo. No Dynamics 365 for Retail, versão 1611, os layouts compactos sempre têm um teclado numérico completo disponível na tela de transação.

**Painel de totais** - Os painéis de totais podem ser configurados em uma ou duas colunas para exibir campos como contagem de linhas, valor de desconto, encargos, subtotal e imposto. No Dynamics 365 for Retail, versão 1611, os layouts compactos suportam apenas uma coluna de totais. 

**Recibo** - O painel de recibo contém linhas de vendas, linhas de pagamento e informações de entrega para produtos e serviços processados no PDV. Os usuários podem especificar colunas, larguras e posicionamento. Em layouts compactos no Dynamics 365 for Retail, versão 1611, você também pode configurar informações adicionais que aparecerão na linha abaixo da linha principal. 

**Cartão de cliente** - O cartão de cliente mostra informações relativas ao cliente atualmente associado à transação. O cartão de cliente pode ser configurado para ocultar ou exibir informações adicionais. 

**Controle de guia** - O controle de guia pode ser colocado no layout da tela, e outros controles como o teclado numérico, o cartão do cliente, ou as grades de botões podem ser colocados na guia. O controle de guias é um contêiner que ajuda os usuários a colocar mais informações na tela. O controle de guias está disponível apenas para layouts completos. 

**Imagem** - O controle de imagem pode ser usado para mostrar o logotipo de armazenamento ou outra imagem de marca na tela de transação. O controle de imagem está disponível apenas para layouts completos. 

**Produtos recomendados** - Se configurados para o ambiente, os controles dos produtos recomendados mostrarão sugestões de produto baseadas no aprendizado da máquina. O controle de produtos recomendados só está disponível para layouts completos no Dynamics 365 for Retail, versão 1611. **Controle personalizado **- O controle personalizado age como um substituto dentro do layout de tela para permitir que os usuários reservem espaço para conteúdo personalizado. O controle personalizado está apenas disponível para layouts completos.

<a name="see-also"></a>Consulte também
--------

[Instalar o designer do layout de PDV de varejo](install-pos-layout-designer.md)




