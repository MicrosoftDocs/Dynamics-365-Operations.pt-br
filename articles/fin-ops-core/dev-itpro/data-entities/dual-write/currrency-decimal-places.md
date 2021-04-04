---
title: Migração de tipo de dados de moeda para gravação dupla
description: Este tópico descreve como alterar o número de casas decimais que a gravação dupla permite para moeda.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-04-06
ms.openlocfilehash: 78820ff49958fc3b474038c0fcd126bcf6886d0d
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560814"
---
# <a name="currency-data-type-migration-for-dual-write"></a>Migração de tipo de dados de moeda para gravação dupla

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Você pode aumentar o número de casas decimais com suporte para os valores de moeda para um máximo de 10. O limite padrão é quatro casas decimais. Ao aumentar o número de casas decimais, você ajuda a prevenir a perda de dados usando a gravação dupla para sincronizar dados. O aumento no número de casas decimais é uma alteração de adesão. Para implementá-la, é necessário solicitar assistência da Microsoft.

O processo de alterar o número de casas decimais tem duas etapas:

1. Solicite a migração da Microsoft.
2. Altere o número de casas decimais no Dataverse.

O aplicativo Finance and Operations e o Dataverse devem oferecer suporte ao mesmo número de casas decimais nos valores de moeda. Caso contrário, pode haver perda de dados quando essas informações forem sincronizadas entre aplicativos. O processo de migração reconfigura a maneira como os valores de moeda e da taxa de câmbio são armazenados, mas não altera nenhum dado. Após a conclusão da migração, é possível aumentar o número de casas decimais para códigos de moeda e preços, e os dados que os usuários inserem e visualizam poderão ter maior precisão decimal.

A migração é opcional. Se você puder se beneficiar com o suporte para mais casas decimais, recomendamos que considere a migração. As organizações que não exigem valores com mais de quatro casas decimais não precisam migrar.

## <a name="requesting-migration-from-microsoft"></a>Solicitando a migração da Microsoft

O armazenamento para colunas de moeda existentes no Dataverse não pode oferecer suporte para mais de quatro casas decimais. Portanto, durante o processo de migração, os valores de moeda são copiados para novas colunas internas no banco de dados. Esse processo ocorre continuamente até que todos os dados tenham sido migrados. Internamente, no final da migração, os novos tipos de armazenamento substituem os tipos de armazenamento antigos, mas os valores dos dados permanecem inalterados. As colunas de moeda podem oferecer suporte para até 10 casas decimais. Durante o processo de migração, o Dataverse pode continuar sendo usado sem interrupção.

Ao mesmo tempo, as taxas de câmbio são modificadas para que ofereçam suporte para até 12 casas decimais em vez do limite atual de 10. Essa alteração é necessária para que o número de casas decimais seja o mesmo no aplicativo Finance and Operations e no Dataverse.

A migração não altera os dados. Depois que as colunas de moeda e taxa de câmbio forem convertidos, os administradores podem configurar o sistema para usar até 10 casas decimais para colunas de moeda ao especificar o número de casas decimais para cada moeda da transação e para preços.

### <a name="request-a-migration"></a>Solicitar uma migração

Para disponibilizar esse recurso, envie um email para **CDSExpandDecimal@microsoft.com** e inclua as seguintes informações:

+ **Assunto:** Solicitação para habilitar o suporte decimal expandido para \<organizationID\>
+ **Corpo:** Gostaria de habilitar o suporte decimal expandido para a minha organização \<organizationID\>.

Um representante da Microsoft entrará em contato dentro de dois a três dias úteis para as próximas etapas.

Ao solicitar uma migração, esteja ciente dos seguintes detalhes e estabeleça um plano de forma adequada:

+ O tempo necessário para migrar os dados depende da quantidade de dados no sistema. A migração de bancos de dados grandes pode demorar vários dias.
+ O tamanho do banco de dados aumenta temporariamente enquanto a migração está sendo executada, pois é necessário espaço adicional para os índices. A maior parte do espaço adicional é liberada quando a migração é concluída.
+ Durante o processo de migração, se ocorrerem erros que impedem a conclusão da migração, o sistema gera alertas para o Suporte da Microsoft, para que a equipe de Suporte possa intervir. No entanto, mesmo se ocorrer erros durante a migração, o Dataverse permanecerá totalmente disponível para uso regular.
+ O processo de migração é irreversível.

## <a name="changing-the-number-of-decimal-places"></a>Alterar o número de casas decimais

Depois que a migração for concluída, o Dataverse pode armazenar números com mais casas decimais. Os administradores podem escolher quantas casas decimais são usadas para códigos de moeda específicos e para preços. Os usuários do Microsoft Power Apps, Power BI e Power Automate podem exibir e usar números com mais casas decimais.

Para fazer essa alteração, atualize as seguintes configurações no Power Apps:

+ **Configurações do Sistema: Precisão da moeda para precificação** – A coluna **Defina o número de decimais da moeda que será usada para precificação em todo o sistema** define como a moeda se comportará para a organização quando **Precisão de preço** for selecionado.
+ **Gerenciamento de Negócios: Moedas** – A coluna **Precisão da Moeda** permite especificar um número personalizado de casas decimais para uma moeda específica. Há um fallback para a configuração em toda a organização.

Estas são algumas limitações:

+ Não é possível configurar a coluna de moeda em uma tabela.
+ Você pode especificar mais de quatro casas decimais somente nos níveis **Preço** e **Moeda de Transação**.

### <a name="system-settings-currency-precision-for-pricing"></a>Configurações do Sistema: Precisão da moeda para precificação

Após a conclusão da migração, os administradores podem definir a precisão da moeda. Vá para **Configurações \> Administração** e selecione **Configurações do Sistema**. Em seguida, na guia **Geral**, altere o valor da coluna **Definir o número de decimais da moeda que será usada para precificação em todo o sistema**, conforme mostrado na ilustração a seguir.

![Configurações do sistema para moeda](media/currency-system-settings.png)

### <a name="business-management-currencies"></a>Gerenciamento de Negócios: Moedas

Se quiser que a precisão de uma moeda específica seja diferente da precisão da moeda usada para os preços, é possível alterá-la. Vá para **Configurações \> Gerenciamento de Negócios**, selecione **Moedas** e selecione a moeda a ser alterada. Em seguida, defina a coluna **Precisão da Moeda** com o número de casas decimais que deseja, conforme mostrado na ilustração a seguir.

![Configurações de moeda para uma localidade específica](media/specific-currency.png)

### <a name="tables-currency-column"></a>tabelas: coluna Moeda

O número de casas decimais que podem ser configuradas para colunas de moeda específicas é limitado a quatro.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]