---
title: Visão geral de políticas de compras
description: Este artigo fornece informações sobre diretivas de compras. Uma política de compra é um conjunto de regras que controlam o processo da requisição. As políticas de compra ajudam administradores de compras a implementar sua estratégia de compras criando uma estrutura de política alinhada às necessidades de compras estratégicas da organização.
author: RichardLuan
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchReqSourcingPolicyRule, SysPolicy, SysPolicyListPage, PurchReqControlRule, RequisitionReplenishCatAccessPolicyRule, PurchReApprovalPolicyRule, RequisitionReplenishControlRule, PurchReqControlRFQRule
audience: Application User
ms.reviewer: kamaybac
ms.custom: 11614
ms.assetid: 729a304d-0f3f-4ccb-bd5b-46ee0976c57f
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a8c8fa3e4b59cdb013c1c524e06085b06905715e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5215880"
---
# <a name="purchasing-policies-overview"></a>Visão geral de políticas de compras

[!include [banner](../includes/banner.md)]

Este artigo fornece informações sobre diretivas de compras. Uma política de compra é um conjunto de regras que controlam o processo da requisição. As políticas de compra ajudam administradores de compras a implementar sua estratégia de compras criando uma estrutura de política alinhada às necessidades de compras estratégicas da organização.

Uma política de compras consiste em um conjunto de regras de política. Quando você define uma regra de política, primeiro seleciona um tipo de regra. Então, você cria uma regra para o tipo de regra definindo as configurações, a data de início e a data de término da regra.  

Por exemplo, um administrador cria uma política, selecione o tipo de regra de **Política de catálogo** e então adicione uma regra de política de catálogo à política. Essa regra de política de catálogo especifica que o catálogo da Adventure deve ser usado para compras internas. Depois que a política de compras é associada a uma organização em particular, os funcionários dessa organização veem o catálogo da Adventure quando criam requisições.

## <a name="assigning-policies-to-organizations"></a>Atribuindo políticas a organizações
Antes que uma política entre em vigor, ela deverá ser associada a uma organização. As políticas de compras estão associadas à finalidade da hierarquia de **Controle interno de compras**. Portanto, as políticas de compras só se aplicam às organizações em hierarquias com a finalidade de hierarquia de **Controle interno de compras**. Você também pode selecionar organizações na lista simples de entidades legais na tabela CompanyInfo. Essas entidades legais são designadas na estrutura de política como "Empresas".

## <a name="determining-which-rule-to-apply"></a>Determinando que regra será aplicada
Dependendo da forma como as políticas de compras são configuradas, várias regras poderão afetar os usuários em uma organização. Os exemplos a seguir ilustram as diferentes maneiras nas quais você pode configurar políticas de compras e especificar como as políticas são aplicadas quando ocorre uma transação.

### <a name="example-1-simple-purchasing-policy-configuration"></a>Exemplo 1: Configuração de política de compras simples

As organizações pequenas e menos complexas podem configurar políticas de compras por entidade legal e podem usar somente a Hierarquia da organização de empresas.  

Para a Fabrikam, uma pequena empresa, as necessidades de compras variam pouco na organização. As regras de compras variam somente entre as entidades legais da organização. Por exemplo, os funcionários da Fabrikam no Canadá e os funcionários da Fabrikam nos EUA compram mercadorias e serviços de catálogos diferentes e de fornecedores diferentes. Portanto, a Fabrikam configura suas políticas de compras no nível da entidade legal.  

A Fabrikam cria duas políticas de compras. A política A aplica-se a sua entidade legal dos EUA, 1111. A política B aplica-se a sua entidade legal do Canadá, 2222. Quando um funcionário na entidade legal 1111 cria uma requisição de compra, as regras de diretivas são derivadas da diretiva A. Por exemplo, o catálogo de produtos do funcionário especificado consulta as regras de diretiva do catálogo da diretiva A.  

Quando um funcionário na entidade legal 2222 cria uma requisição de compra, as regras de diretivas são derivadas da diretiva B.  

**Observação:** Se um funcionário da entidade legal 1111 comprar um item em nome de um funcionário da pessoa jurídica 2222, as regras de política especificadas para a entidade legal 2222 (que é, as regras de política da política B), serão aplicadas.

### <a name="example-2-complex-purchasing-policy-configuration"></a>Exemplo 2: Configuração de política de compras complexas

No exemplo anterior, todas as regras de compra foram definidas em uma única hierarquia da organização, a hierarquia da organização Empresas. Entretanto, uma organização complexa pode definir políticas para várias hierarquias da organização.  


A Contoso é uma grande empresa que exige regras de compras complexas para controlar o processo de requisição. A Contoso definiu regras para duas hierarquias da organização diferentes: controle de compras Departamento e Global.  

A política 123 é definida para a hierarquia da organização Departamento para Vendas no Reino Unido – departamento de vendas. Na política 123, a regra de controle de requisição de compra especifica que as restrições devem ser impostas para as quantidades mínimas de ordem. Nessa regra, a opção **Impor restrições de quantidade mínima de ordem** está selecionada.  

A política 456 é definida para a hierarquia organizacional de controle de compras globais para o departamento de Vendas e Marketing. Na política 456, a regra de controle de requisição de compra não especifica que se deve impor restrições de quantidade mínima de ordem. Nessa regra, a opção **Impor restrições de quantidade mínima de ordem** está desmarcada.  

Samuel trabalha no departamento de vendas Reino Unido – Vendas, no escritório da Contoso, no Reino Unido. As políticas para as hierarquias da organização de controle de compras Departamento e Global se aplicam a esse departamento. Quando Samuel cria uma requisição de compra, o sistema deve determinar qual política deve ser aplicada. O administrador do sistema configura os parâmetros da política de compras para especificar que as políticas de compras devem ser aplicadas na seguinte ordem de precedência:

1.  Controle de compras globais
2.  Departamento
3.  Empresas

Consequentemente, a política 456 é aplicada à requisição de compra criada por Sam, e nenhuma quantidade mínima de ordem é necessária para a requisição de compra.

## <a name="policy-rules"></a>Regras de política
### <a name="catalog-policy-rule"></a>Regra de política de catálogo

A regra de política do catálogo determina o que os usuários do catálogo de compras verão quando criarem requisições de compra. Se um usuário tiver permissão para solicitar produtos em nome de outro usuário, a requisição usará a regra de política de catálogo definida para a entidade legal do solicitante e a unidade operacional determinar qual catálogo exibir. Para que seja possível definir uma regra de política de catálogo, você deve criar e publicar um catálogo de compras.

### <a name="category-access-policy-rule"></a>Regra de política de acesso de categoria

A regra de política de acesso de categoria determina quais usuários de categorias terão acesso ao criar requisições de compra. Se nenhuma regra for especificada, todas as categorias de comprar poderão ser adicionadas à requisição de compra.

1.  Selecione a opção **Incluir regra pai** para aplicar a regra de política de acesso de categoria da organização pai à categoria.
2.  No painel de **Categorias disponíveis**, selecione as categorias ao qual a regra se aplica. Quando você seleciona uma categoria, todas as categorias que estão mais alto na hierarquia também serão adicionadas à lista **Categorias selecionadas**.
3.  Selecione a opção **Incluir subcategorias** para aplicar a regra para todas as subcategorias da categoria selecionada.

### <a name="category-policy-rule"></a>Regra de política de categoria

A regra de política de categoria define como os usuários podem selecionar fornecedores para cada categoria. Também define os requisitos para os processos de recebimento e de faturamento.

### <a name="re-approval-rule-for-purchase-orders"></a>Regra de reaprovação de ordens de compra

A regra de nova aprovação é uma regra opcional que define os critérios para exigir a reaprovação quando uma ordem de compra for alterada. Os campos selecionados são avaliados no fluxo de trabalho da ordem de compra quando a condição "Exige reaprovação da ordem de compra" for configurada no fluxo de trabalho.

> [!NOTE]
> A distribuição contábil sempre será redefinida quando uma ordem de compra aprovada com gerenciamento de alterações habilitado for alterada. Sendo assim, saiba que se você quiser evitar uma reaprovação de uma ordem de compra quando determinados campos forem alterados, o campo Distribuição contábil alterado NÃO deverá ser incluído como um campo selecionado para reaprovação. 

### <a name="purchase-requisition-rfq-rule"></a>Regra de RFQ de requisição de compra

A regra RFQ de requisição de compra:define os critérios para exigir uma solicitação de cotação (RFQ) para uma linha de requisição de compra. Se uma linha atender às condições, o carimbo "RFQ informal“ ou “RFQ formal” aparecerá na linha da requisição.

### <a name="purchase-requisition-control-rule"></a>Regra de controle de requisição de compra

A regra de controle de requisição de compra para requisições do tipo **consumo** é uma regra opcional. Ao criar regras desse tipo, você poderá definir opções em várias guias:

-   Na guia **Envio do fluxo de trabalho**, você pode configurar os campos que devem ser inseridos na linha da requisição para a requisição a ser enviada para aprovação.
-   Na guia **Quantidades da ordem**, você pode configurar os campos necessários à requisição de compra em certas condições. Também é possível impor as quantidades da ordem.
-   Na guia **Datas** você pode configurar se a data contábil é igual à data solicitada
-   Na guia **Endereço**, você pode definir se é permitido para o usuário criar novos endereços no sistema a serem aplicados à requisição de compra.

### <a name="requisition-purpose-rule"></a>Regra de finalidade da requisição

A regra de finalidade de requisição é uma regra opcional que determina o tipo de finalidade da requisição permitida para uma entidade legal específica. A menos que outra finalidade seja indicada nessa regra, as requisições terão automaticamente uma finalidade **Consumo** quando forem criadas.

### <a name="replenishment-category-access-policy-rule"></a>Regra de política de acesso à categoria de reabastecimento

A regra de política de acesso da categoria de reabastecimento é uma regra opcional que determina os produtos disponíveis para atender à demanda de requisição para uma entidade legal específica quando a finalidade da requisição for **Reabastecimento**.

### <a name="replenishment-control-rule"></a>Regra de controle de reabastecimento

A regra de controle de reabastecimento é uma regra opcional que define os campos que devem ser inseridos na linha de requisição para a requisição a ser enviada para aprovação quando a finalidade da requisição for **Reabastecimento**.

### <a name="purchase-order-creation-and-demand-consolidation-rule"></a>Criação de ordem de compra e regra de consolidação de demanda

A regra de consolidação de criação e a demanda de ordem de compra define as regras de diretiva a serem usadas quando uma ordem de compra é gerada a partir de uma requisição de compra aprovada. Ao criar regras desse tipo, você poderá definir opções em várias guias:

-   Na guia **Divisão da ordem de compra**, você pode definir critérios para dividir linhas de requisição de compra em ordens de compra separadas.
-   Na guia **Transferência de preço/desconto**, você pode definir quando recalcular o contrato de preço quando uma ordem de compra é criada:
    -   **Somente se não houver um contrato comercial** – os preços e os descontos só serão transferidos da requisição de compra se não houver um contrato comercial ou um preço base aplicável. Se houver um contrato comercial ou um preço base para o item ou o fornecedor, os preços e os descontos serão recalculados com base no contrato comercial ou no preço base e aplicados à ordem de compra. A menos que especificado o contrário, este é o comportamento padrão.
    -   **Sempre** – os preços e os descontos são sempre transferidos da requisição de compra.

    Você também pode permitir que o solicitante altere o método de preço e a transferência de desconto para linhas de requisição de compra individuais, independentemente da regra de transferência de preço/desconto definida. Selecione a opção **Permitir substituição manual por linha da requisição de compra** caso você queira habilitar essa capacidade.
-   Na guia **Transferência da descrição do item** você poderá transferir a descrição do item da requisição quando ela se originar de uma RFQ.
-   Na guia **Tolerância de Preço**, você define as regras de tolerância de preços que serão usadas para rotear requisições de compra aprovadas anteriores ao processo de revisão quando o preço de um item de catálogo de compras aumentar. Defina o valor máximo que o valor líquido em um item de linha em uma requisição de compra pode aumentar entre a hora quando a requisição de compra é aprovada e a hora quando a ordem de compra é criada. O valor líquido é calculado usando a seguinte fórmula: (\[Quantidade x (Preço unitário – Desconto) ÷ Preço unitário\] + Encargos diversos de compra) x (100 - Porcentagem do desconto) ÷ 100. As linhas da requisição de compra que excederem a tolerância de preço definida serão mantidas para o processamento manual. As regras que você configura na guia **Processamento de erros** determinam como as linhas de requisição de compra são processadas.
-   Na guia **Processamento de erros**, você pode configurar a regra de processamento aplicada a uma requisição de compra se a validação falhar durante a criação da ordem de compra por causa de um erro do fornecedor ou a um erro de tolerância de preços. Selecione uma das seguintes opções:
    -   **Nenhuma ação** – as linhas de requisição de compra permanecem na página **Liberar requisições de compra aprovadas**. O status das linhas de requisição de compra permanece como **Aprovada**. Entretanto, os erros devem ser resolvidos antes que uma ordem de compra possa ser gerada para as linhas de requisição de compra.
    -   **Cancelar a linha da requisição de compra** – as linhas da requisição de compra são canceladas. O solicitante pode criar uma nova requisição de compra para as linhas canceladas se ainda quiser solicitar os itens de linha.
    -   **Criar uma nova linha da requisição de compra** – as linhas da requisição de compra são canceladas. As novas requisições de compra são então geradas e contêm somente as linhas de requisição de compra cuja validação falhou. As novas requisições de compra geradas têm um status **Rascunho**. Essas requisições de compra podem ser reenviadas novamente para revisão depois que os erros de validação forem resolvidos. O preparador das linhas de requisição de compra é notificado de que as linhas foram canceladas e as novas requisições de compra foram geradas para as linhas de requisição de compra que falharam.
-   Na guia **Criação manual de ordem de compra**, você pode definir os parâmetros que determinam se uma requisição de compra deve ser processada manualmente ou se ela pode ser automaticamente convertida em uma ordem de compra. Os parâmetros podem ser aplicadas a itens de catálogo interno, a itens de catálogo externo ou a itens não catalogados. Selecione uma das seguintes opções:
    -   **Criar manualmente ordens de compra** – crie ordens de compra manualmente para todas as requisições de compra.
    -   **Criar automaticamente ordens de compra** – crie ordens de compra automaticamente para todas as requisições de compra aprovadas. Nenhuma requisição de compra é mantida para a criação da ordem de compra manual.
    -   **Criar automaticamente ordens de compra, exceto sob estas condições** – crie ordens de compra manualmente para requisições de compra que correspondam aos critérios definidos por você. Todas as outras requisições de compra que foram aprovadas são convertidas automaticamente em ordens de compra. Se você selecionar **Criar automaticamente ordens de compra, exceto sob estas condições**, poderá adicionar as categorias de compras e fornecedores para especificar que as linhas de requisição de compra aprovadas sejam mantidas para processamento manual. Essa opção só pode ser aplicada a itens de catálogo interno, a itens de catálogo externo e a itens não catalogados. Quando você seleciona uma categoria de compras, todas as subcategorias dessa categoria de compras também são selecionadas. Selecione a opção **Todas** para um tipo específico de linha de requisição de compra para conter todas as linhas do tipo de linha para o processamento manual.

    Se desejar que as ordens de compra sejam geradas automaticamente a partir de requisições de compra aprovadas quando o trabalho em lotes para a geração da ordem de compra for executado, selecione a opção **Executar criação automática de ordem de compra como um trabalho em lotes**. Esta opção só se aplica às requisições de compra que não exigem processamento manual. Ao executar a geração automática de ordens de compra como um trabalho em lotes, você poderá planejar a atividade para um momento em que os recursos estejam menos restritos. Se a opção **Pagamento necessário** estiver selecionada nas linhas da requisição de compra, selecione a opção **Quando a requisição for configurada para pré-pagamento** para manter as requisições de compra aprovadas para processamento manual. As requisições de compra mantidas para processamento manual podem ser filtradas, de forma que você possa exibir apenas as linhas de requisição de compra que exijam pagamento antecipado.
-   Na guia **Consolidação de demanda**, você pode definir os parâmetros que determinam se as requisições de compra que são processadas manualmente podem ser consideradas para consolidação de requisição de compra. Os parâmetros podem ser aplicadas a itens de catálogo interno, a itens de catálogo externo ou a itens não catalogados. Selecione uma das seguintes opções:
    -   **Não permitir a consolidação de demanda** – nenhuma linha de requisição de compra aprovada estará qualificada para a consolidação de demanda. Essa opção é selecionada por padrão e se aplica somente às linhas de requisição de compra que exigem processamento manual para a criação da ordem de compra.
    -   **Sempre permitir a consolidação de demanda** – todas as linhas de requisição de compra aprovadas estarão qualificadas para a consolidação de demanda. **Observação:** se você selecionar a opção **Sempre permitir consolidação de demanda** na guia **Consolidação de demanda**, mas se selecionar a opção **Criar automaticamente ordens de compra** na guia **Criação manual da ordem de compra**, todas as requisições de compra serão mantidas para processamento manual.
    -   **Permitir a consolidação de demanda sob estas condições** – defina os critérios que determinam se as linhas de requisição de compra aprovadas estão qualificadas para a consolidação de demanda. Para cada tipo de linha de requisição de compra, você pode definir os critérios por categoria de compras e fornecedor. Se você selecionar **Permitir consolidação de demanda sob estas condições**, poderá definir os critérios por categoria de compras e fornecedor para cada tipo de linha de requisição de compra. Quando você seleciona uma categoria de compras, todas as subcategorias dessa categoria de compras também são selecionadas. Se você selecionar a opção **Todas** para um tipo de linha específica, todas as linhas de requisição de compra daquele tipo de linha estarão qualificadas para consolidação de demanda.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]