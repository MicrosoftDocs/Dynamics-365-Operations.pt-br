---
title: Configurar layouts de tela do POS
description: "Este tópico fornece informações sobre layouts de tela para Microsoft Dynamics 365 para operações - experiências varejistas (POS) do ponto de venda."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application user
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 90573
ms.assetid: a6868f93-02ed-4928-9f6a-3b7383e7e399
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: d49c5c9773047940e524c71e59a674ebe8460ad7
ms.lasthandoff: 03/31/2017


---

# <a name="configure-screen-layouts-for-pos"></a>Configurar layouts de tela do POS

Este tópico fornece informações sobre layouts de tela para Microsoft Dynamics 365 para operações - experiências varejistas (POS) do ponto de venda.

Microsoft Dynamics 365 operações - para a interface de usuário de varejo de (POS) da venda pode ser configurada em uma combinação de perfis e layouts de tela visual, atribuído às lojas, os registros, a usuários e/ou.

## <a name="visual-profile"></a>Perfil visual
Os perfis visuais são atribuídos aos registros e usados para especificar os elementos visual que são específicos registro (e não nos usuários. Qualquer usuário que registrar em registro terá o mesmo tema, cores, e imagens. ** O número do perfil - ** o número do perfil é o identificador exclusivo do perfil visual. ** ** A descrição - a descrição permite que você especifique um nome significativo que ajuda a identificar o perfil correto para sua situação. ** O tema ** - usuários dispõe temas ou escuros claro de aplicativo. Essas configurações afetam a fonte e de plano de fundo descritivo no. ** A cor de acentuação ** - a cor de acentuação é usada no retail para diferenciar ou realce alguns elementos visual como caixas, botões de comando, ou hiperlinks. Esses elementos são normalmente acionáveis. ** Cor de cabeçalho ** - a cor do cabeçalho permite que o usuário para configurar a cor do cabeçalho de página para atender as necessidades da marcagem ferro quente de fornecedor. Esse recurso estará disponível apenas em dynamics 365 para a versão 1611 de operações. ** Planos de fundo de logon - ** usuários pode especificar uma imagem de plano de fundo da tela de logon. O tamanho de arquivo de imagens de segundo plano deve ser mantido como pequena, como quanto possível armazenar e carregue grandes arquivos pode ter um impacto no comportamento e no desempenho do aplicativo. ** O plano de fundo de aplicativos - ** POS também pode usar uma imagem como plano de fundo todo o aplicativo no lugar de cor contínua de tema. Como com planos de fundo logon, recomenda-se manter o tamanho de arquivo como mínimo possível.

## <a name="screen-layouts"></a>Layouts da tela
O layout da tela determina as ações, o conteúdo, e o posicionamento de controles de interface de usuário na tela de tela de boas-vindas e transação POS. ** O tela de boas-vindas ** - a maioria dos casos, a tela de boas-vindas está a página que os usuários verão quando registram em log primeiro no POS. A tela de boas-vindas pode consistir em uma imagem da marcagem ferro quente e as grades de botões que dão acesso operações POS. Normalmente, as operações que não são específicos à transação atual são colocadas aqui. ** A tela da transação - ** a tela da transação é a tela principal do retail para processar transações e ordens de venda. A tela da transação pode ser configurada no designer do layout da tela. ** A tela inicial padrão ** alguns - fornecedores prefere que o caixa navega em diretamente na tela da transação após logon. A configuração padrão do tecido inicial permite que os usuários para cada definiam esse layout da tela.

### <a name="assignment"></a>Atribuição

Os layouts de tela podem ser atribuídos à loja, registro, nível ou de usuário. A atribuição de usuários à atribuição da registradora e armazenamento, e a atribuição de registro à atribuição de lojas. Em um cenário simples onde todos os usuários o usem mesmo layout independentemente do registro ou a função, o layout da tela pode ser definido apenas em lojas. Em alguns casos onde os registros ou usuários precisam layouts especializados, podem ser atribuídos apropriadamente.

### <a name="layout-sizes"></a>Tamanhos de layout

Esse recurso só se aplica para dynamics 365 para a versão 1611 de operações. Porque em muitos casos layouts de tela podem ser usados pelos vários tamanhos do tecido e resoluções de, os usuários poderão configurar o layout e conteúdo de cada um. O aplicativo POS escolherá automaticamente o próximo tamanho do layout do dispositivo no momento de inicialização. Um layout da tela pode também conter para configurações completa e dispositivos de estojo compacto. Essa configuração permite que o usuário é atribuído a um único layout da tela que funcionará nos vários tamanhos de formulários e fatoras no armazenamento. ** O retail moderno - total ** - layouts completas é aconselhável usado para maiores exibe como monitores ou do PC. tablet Os usuários podem escolher que os elementos da interface de usuário determinam incluir, tamanho e posicionamento, e configurar as propriedades detalhadas. Os layouts completas suportam configurações de retrato ou de paisagem. ** O retail moderno - estojo - compacto ** layouts compactos é aconselhável usado para telefones ou baixos. tablet Design das possibilidades são limitadas para dispositivos compactos. Os usuários poderão configurar as colunas e campos para recebimento e totais dos painéis.

### <a name="screen-layout-designer"></a>Designer do layout da tela

Cada tamanho do layout em um layout da tela deve ser configurado usando o designer do layout da tela. O designer permite que os usuários especifiquem e configurem elementos de interface de usuário da tela da transação. O designer do layout da tela ClickOnce usa para baixar e instalar, iniciar, sempre a versão mais recente de aplicativos dos usuários acessa ele. Verifique verificar os requisitos de ClickOnce- navegador para usar alguns browsers, como Chrome, requer extensões. ** O teclado numérico - ** o teclado numérico é o usuário na tela principal da transação POS. Pode ser configurada para mostrar o teclado virtual inteira ideal é que, para écrans sensíveis, somente o campo de entrada, que pode ser usado com um teclado físico. As configurações de teclado numérico disponíveis em layout completo apenas. Em dynamics 365 para a versão 1611 de operações, compactos layouts sempre têm o teclado do número total disponível da tela da transação. ** O painel dos totais ** o painel de total pode ser configurado em um ou outro uma ou duas colunas para exibir campos como linha contagem, o valor de desconto, encargos, o subtotal, e os impostos. Em dynamics 365 para a versão 1611 de operações, compactos layouts suportam somente uma única coluna dos totais. ** Recebimento ** - ** ** o painel de recebimento contém as linhas de venda, o pagamento, e as informações de entrega dos produtos e serviços processados no POS. Os usuários podem determinar, colunas, e larguras posicionamento. Em compactos layouts em dynamics 365 para a versão 1611 de operações, você também pode configurar informações adicionais que aparecerá na linha na linha principal. ** O cartão do cliente - ** o cartão de informações mostra a que pertence ao cliente associado com atualmente a transação. O cartão do cliente pode ser configurado para ocultar ou exibir informações adicionais. ** O controle de guia ** - o controle de guia pode ser colocado no layout da tela, e outros controles como teclado numérico, o cartão do cliente, ou as grades de botões podem ser colocadas de guia. Controle de guias é um contêiner que ajuda os usuários acordo com mais informações na tela. O controle de guia está disponível apenas para layouts completas. ** Imagem ** - o controle de imagem pode ser usado para mostrar o logotipo de armazenamento ou outra marcagem a imagem de ferro quente na tela da transação. Controle de imagem está disponível somente layouts para concluído. ** Produtos recomendados ** - se configuradas para o ambiente, o controle de produtos recomendado mostrará as indicações de produto com base em saber de computador. Controle de produtos é recomendável somente disponível para layouts completas em dynamics 365 para a versão 1611 de operações. ** O controle personalizado ** - o controle personalizado atua como um espaço reservado no layout da tela permite que os usuários reservem espaço para o conteúdo personalizada. Controle personalizado está disponível somente layouts para concluído.

<a name="see-also"></a>Consulte também
--------

[Install the Retail POS Layout designer](install-pos-layout-designer.md)


