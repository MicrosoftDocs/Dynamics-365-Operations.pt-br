---
title: Migração de tipo de dados de moeda para gravação dupla
description: Este artigo descreve como alterar o número de casas decimais que a gravação dupla permite para moeda.
author: RamaKrishnamoorthy
ms.date: 12/08/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-04-06
ms.openlocfilehash: 809906c3926b200e7beac84e780314aec1f8c2ca
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8855577"
---
# <a name="currency-data-type-migration-for-dual-write"></a>Migração de tipo de dados de moeda para gravação dupla

[!include [banner](../../includes/banner.md)]



Você pode aumentar o número de casas decimais com suporte para os valores de moeda para um máximo de 10. O limite padrão é quatro casas decimais. Ao aumentar o número de casas decimais, você ajuda a prevenir a perda de dados usando a gravação dupla para sincronizar dados. O aumento no número de casas decimais é uma alteração de adesão. Para implementá-la, é necessário solicitar assistência da Microsoft.

O processo de alterar o número de casas decimais tem duas etapas:

1. Solicite a migração da Microsoft.
2. Altere o número de casas decimais no Dataverse.

O aplicativo de Finanças e Operações e o Dataverse devem oferecer suporte ao mesmo número de casas decimais e, valores de moeda. Caso contrário, pode haver perda de dados quando essas informações forem sincronizadas entre aplicativos. O processo de migração reconfigura a maneira como os valores de moeda e da taxa de câmbio são armazenados, mas não altera nenhum dado. Após a conclusão da migração, é possível aumentar o número de casas decimais para códigos de moeda e preços, e os dados que os usuários inserem e visualizam poderão ter maior precisão decimal.

A migração é opcional. Se você puder se beneficiar com o suporte para mais casas decimais, recomendamos que considere a migração. As organizações que não exigem valores com mais de quatro casas decimais não precisam migrar.

## <a name="requesting-migration-from-microsoft"></a>Solicitando a migração da Microsoft

O armazenamento para colunas de moeda existentes no Dataverse não pode oferecer suporte para mais de quatro casas decimais. Portanto, durante o processo de migração, os valores de moeda são copiados para novas colunas internas no banco de dados. Esse processo ocorre continuamente até que todos os dados tenham sido migrados. Internamente, no final da migração, os novos tipos de armazenamento substituem os tipos de armazenamento antigos, mas os valores dos dados permanecem inalterados. As colunas de moeda podem oferecer suporte para até 10 casas decimais. Durante o processo de migração, o Dataverse pode continuar sendo usado sem interrupção.

Ao mesmo tempo, as taxas de câmbio são modificadas para que ofereçam suporte para até 12 casas decimais em vez do limite atual de 10. Essa alteração é necessária para que o número de casas decimais seja o mesmo no aplicativo de Finanças e Operações e no Dataverse.

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

Após a conclusão da migração, os administradores podem definir a precisão da moeda. Acesse **Configurações \> Administração** e selecione **Configurações do Sistema**. Em seguida, na guia **Geral**, altere o valor da coluna **Definir o número de decimais da moeda que será usada para precificação em todo o sistema**, conforme mostrado na ilustração a seguir.

![Configurações do sistema para moeda.](media/currency-system-settings.png)

### <a name="business-management-currencies"></a>Gerenciamento de Negócios: Moedas

Se quiser que a precisão de uma moeda específica seja diferente da precisão da moeda usada para os preços, é possível alterá-la. Acesse **Configurações \> Gerenciamento de Negócios**, selecione **Moedas** e selecione a moeda a ser alterada. Em seguida, defina a coluna **Precisão da Moeda** com o número de casas decimais que deseja, conforme mostrado na ilustração a seguir.

![Configurações de moeda para uma localidade específica.](media/specific-currency.png)

### <a name="tables-currency-column"></a>Tabelas: coluna Moeda

O número de casas decimais que podem ser configuradas para colunas de moeda específicas é limitado a quatro.

### <a name="default-currency-decimal-precision"></a>Precisão decimal da moeda padrão
Para obter o comportamento esperado da precisão decimal da moeda padrão em cenários de migração e de não migração, consulte a tabela a seguir. 

| Data de criação  | Campo decimal da moeda    | Organização existente (campo Moeda não migrado) | Organização existente (campo Moeda migrado) | Nova organização criada após o build 9.2.21062.00134 |
|---------------------------------------------------------|-------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------|------------------------------------------------|
| Campo Moeda criado antes do build 9.2.21111.00146  |     |  |       |
|    | Precisão máxima visível na interface do usuário   | 4 dígitos    | 10 dígitos    | N/D    |
| | Precisão máxima visível no banco de dados e na interface do usuário de resultados da consulta de BD         | 4 dígitos   | 10 dígitos   | N/D    |
| Campo Moeda criado depois do build 9.2.21111.00146 |    |  |     |   |
|   | Precisão decimal máxima visível na interface do usuário     | 4 dígitos   | 10 dígitos   | 10 dígitos     |
|          | Precisão decimal máxima visível no banco de dados e na interface do usuário de resultados da consulta de BD | 10 dígitos. No entanto, somente 4 são significativos com todos os zeros além dos 4 dígitos decimais. Isso permite uma migração mais simples e rápida da organização, se necessário. | 10 dígitos      | 10 dígitos     |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
