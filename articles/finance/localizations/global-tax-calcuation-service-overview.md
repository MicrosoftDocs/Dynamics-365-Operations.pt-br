---
title: Visão geral do Cálculo de Imposto
description: Este artigo explica o escopo geral e os recursos do recurso Cálculo de Imposto.
author: EricWangChen
ms.date: 09/08/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.search.form: TaxIntegrationTaxServiceParameters
ms.openlocfilehash: a193db82b2b079c1e10fbfb6bfde7aa43b18bc4a
ms.sourcegitcommit: dbb997f252377b8884674edd95e66caf8d817816
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2022
ms.locfileid: "9465157"
---
# <a name="tax-calculation-overview"></a>Visão geral do Cálculo de Imposto

[!include [banner](../includes/banner.md)]

O Cálculo de Imposto é um serviço multilocatário hiperescalável que permite que o Global Tax Engine automatize e simplifique o processo de determinação e cálculo de imposto. O mecanismo de cálculo de imposto é totalmente configurável. Os elementos que podem ser configurados incluem, entre outros, o modelo de dados tributável, o código de imposto, a matriz de aplicabilidade do imposto e a fórmula de cálculo do imposto. O mecanismo de cálculo de imposto é executado na plataforma de serviços principais do Microsoft Azure e oferece tecnologia moderna e escalabilidade exponencial.

O cálculo de impostos é integrado ao Dynamics 365 Finance e ao Dynamics 365 Supply Chain Management. Futuramente, também será integrado ao Dynamics 365 Project Operations, Dynamics 365 Commerce e a outros aplicativos próprios e de terceiros.

> [!IMPORTANT]
> Ao habilitar o Cálculo de Imposto, algumas operações em dados relacionados podem ser executadas em um data center diferente do data center que mantém os dados do serviço. Revise os [Termos e Condições](https://go.microsoft.com/fwlink/?linkid=2156043) antes de habilitar o Cálculo de Imposto. Sua privacidade é importante para nós. Para saber mais, leia nossa [política de privacidade](https://go.microsoft.com/fwlink/?LinkId=521839).

O Cálculo de Imposto é um mecanismo de imposto baseado em microsserviço que oferece escalabilidade exponencial e pode ajudá-lo a executar as seguintes tarefas:

- Determinar automaticamente o grupo de impostos sobre vendas, o grupo de impostos sobre vendas do item e os códigos de imposto corretos por meio de um mecanismo de determinação aprimorado.
- Suportar vários números de registro de imposto em uma entidade legal e determine automaticamente o número de registro de imposto correto em transações tributáveis.
- Dar suporte a determinação, cálculo, lançamento e liquidação de impostos para ordens de transferência.
- Definir fórmulas e condições de cálculo de imposto configuráveis para suas necessidades comerciais específicas.
- Compartilhar a determinação de imposto e a solução de cálculo em entidades legais para economizar esforços de manutenção e evitar erros.
- Dar suporte à determinação de número de registro de imposto do cliente e do fornecedor.
- Suportar a determinação de código de lista.
- Dar suporte a parâmetros de cálculo de imposto no nível da jurisdição de impostos.

Para usar o Cálculo de Imposto, instale o suplemento de Cálculo de Imposto do projeto no Microsoft Dynamics Lifecycle Services. Em seguida, conclua a configuração no [Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/) e habilite o Cálculo de Imposto no Finance and Supply Chain Management. Para obter mais informações, consulte [Introdução ao serviço de imposto](global-get-started-with-tax-calculation-service.md).

## <a name="availability"></a>Disponibilidade

O Cálculo de Imposto está geralmente disponível em ambientes de produção para todos os clientes a partir da versão 10.0.21.

Novos recursos continuarão sendo entregues. Verifique frequentemente o plano de versão mais atualizado para aprender sobre a cobertura e o escopo dos recursos com suporte.

O Cálculo de Imposto é implantado nas regiões do Azure a seguir. Mais regiões do Azure serão adicionadas, de acordo com as necessidades dos clientes.

- Pacífico Asiático
- Austrália
- Brasil
- Canadá
- Europa
- França
- Índia
- Japão
- África do Sul
- Suíça
- Emirados Árabes Unidos
- Reino Unido
- Estados Unidos

> [!NOTE]
> O Cálculo de Imposto não oferece suporte à versões anteriores do Dynamics 365, como Dynamics AX 2012 ou implantações locais do Dynamics 365.

## <a name="versions"></a>Versões
É recomendável importar e configurar sua configuração de Cálculo do Imposto com a versão que corresponde à sua versão do Finance ou do Supply Chain Management.

| Versão do Finance ou Supply Chain Management | Versão da configuração de imposto               |
| --------------- | --------------------------------------- |
| 10.0.30         | Configuração de Cálculo do Imposto 40.55.239 |
| 10.0.29         | Configuração de Cálculo do Imposto 40.55.236 |
| 10.0.28         | Configuração de Cálculo do Imposto 40.54.234 |
| 10.0.27         | Configuração de Cálculo do Imposto 40.54.234 |


## <a name="data-flow"></a>Fluxo de dados

Aqui está uma descrição do processo de fluxo de dados para o Cálculo de Imposto. 

1. No RCS, exiba e importe configurações de modelo de documento tributável e configurações de mapeamento de modelos. Se você deve estender as configurações para um cenário avançado, consulte [Adicionar campos de dados em configurações de imposto](tax-service-add-data-fields-tax-configurations.md).
2. No RCS, crie ou mantenha os recursos de imposto. Você pode usar os recursos de imposto para manter taxas de imposto e regras de aplicabilidade de imposto.
3. Depois que a configuração do recurso de imposto for concluída, publique as configurações de imposto e os recursos de imposto do RCS para o repositório Global.
4. No Finance, selecione a versão de configuração do recurso de imposto a ser usada para uma entidade legal específica.
5. No Finance and Supply Chain Management, opere as transações como de costume. Quando o Cálculo de Imposto é necessário, o cliente coleta informações da transação, como a ordem de venda ou a ordem de compra, e empacota as informações como conteúdo. Uma solicitação será enviada para calcular o imposto.
6. A solicitação de cálculo de imposto é recebida do cliente e o cálculo é concluído. O resultado do imposto será devolvido para o cliente.
7. O cliente do Dynamics 365 recebe o resultado do imposto e apresenta o resultado do cálculo de imposto em uma página de imposto.

## <a name="supported-transactions"></a>Transações com suporte

O Cálculo de Imposto pode ser habilitado por transações. 

A tabela a seguir lista as transações com suporte na versão correspondente.

| Versão | Transações |
|---------|--------------|
| 10.0.29 | Diários periódicos |
| 10.0.28 | Diário de pagamentos do fornecedor<br> Diário de pagamentos do cliente | 
| 10.0.26 | Diários Gerais<br> Diário de faturas de fornecedores |
| 10.0.23 | Fatura de texto livre |
| 10.0.21| Vendas<br><ul><li>Cotação de Venda</li><li>Ordem de venda</li><li>Confirmação</li><li>Lista de Separação</li><li>Guia de Remessa</li><li>Fatura de venda</li><li>Nota de Crédito</li><li>Ordem de retorno</li><li>Encargos diversos do cabeçalho</li><li>Encargos diversos da linha</li></ul>Compra<br><ul><li>Ordem de Compra</li><li>Confirmação</li><li>Lista de Recebimentos</li><li>Recebimento de produtos</li><li>Fatura de compra</li><li>Encargos diversos do cabeçalho</li><li>Encargos diversos da linha</li><li>Nota de Crédito</li><li>Ordem de retorno</li><li>Requisição de Compra</li><li>Encargos diversos da linha de requisição de compra</li><li>Solicitação de cotação</li><li>Encargos diversos do cabeçalho da solicitação de cotação</li><li>Encargos diversos da linha da solicitação de cotação</li></ul>Inventário<ul><li>Ordem de transferência – enviar</li><li>Ordem de transferência – receber</li></ul>|

## <a name="supported-countriesregions"></a>Países/regiões com suporte

O Cálculo de imposto pode ser executado com recursos de localização com suporte. A tabela a seguir lista os países/regiões para o endereço principal de uma entidade legal:

| Versão | País/região |
|---------|----------------|
| 10.0.26 | - China <br>- República Tcheca<br>- Espanha |
| 10.0.24 | México |
| 10.0.23 | - Tailândia <br>- Japão <br>- Malásia <br>- Singapura |
| 10.0.22 | - Austrália<br>- Barein <br>- Canadá<br>- Egito <br>- RAE de Hong Kong <br>- Kuwait <br>- Nova Zelândia <br>- Omã <br>- Catar <br>- Arábia Saudita <br>- África do Sul <br>- Emirados Árabes Unidos |
| 10.0.21 | - Áustria <br>- Bélgica <br>- Dinamarca <br>- Estônia <br>- Finlândia <br>- França <br>- Alemanha <br>- Hungria <br>- Islândia <br>- Irlanda <br>- Itália <br>- Letônia <br>- Lituânia <br>- Países Baixos <br>- Noruega <br>- Polônia <br>- Suécia <br>- Suíça <br>- Reino Unido <br>- Estados Unidos |

Para qualquer país/região não localizado pela Microsoft, o cálculo de imposto também pode ser habilitado e executado com outros recursos globais.

## <a name="related-resources"></a>Recursos relacionados

[Introdução ao serviço de imposto](./global-get-started-with-tax-calculation-service.md)

[Vários números de registro de IVA](./emea-multiple-vat-registration-numbers.md)

[Suporte ao recurso de imposto para a ordem de transferência](./tasks/tax-feature-support-for-transfer-order.md)

[Como criar uma extensão no serviço de imposto](./tax-service-add-data-fields-tax-integration-by-extension.md)
