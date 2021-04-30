---
title: Configurar integração com o Dayforce
description: A integração entre o Microsoft Dynamics 365 Human Resources e o Ceridian Dayforce depende de várias etapas de configuração descritas neste artigo. Você deve configurar a integração no Human Resources e no Dayforce antes de processar uma execução de pagamento.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PersonnelIntegrationConfiguration
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1647b7fbf84a78051e745e918954df32a2e7e1dd
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5889995"
---
# <a name="configure-integration-with-dayforce"></a><span data-ttu-id="f95f9-104">Configurar integração com o Dayforce</span><span class="sxs-lookup"><span data-stu-id="f95f9-104">Configure integration with Dayforce</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="f95f9-105">A integração entre o Microsoft Dynamics 365 Human Resources e o Ceridian Dayforce depende de várias etapas de configuração descritas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="f95f9-105">The integration between Microsoft Dynamics 365 Human Resources and Ceridian Dayforce relies on several configuration steps that are described in this article.</span></span> <span data-ttu-id="f95f9-106">Você deve configurar a integração no Human Resources e no Dayforce antes de processar uma execução de pagamento.</span><span class="sxs-lookup"><span data-stu-id="f95f9-106">You must configure the integration in both Human Resources and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="f95f9-107">Ao usar um serviço como o Dayforce para concluir execuções de pagamento, é necessário ativar a integração no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f95f9-107">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Human Resources.</span></span> <span data-ttu-id="f95f9-108">A integração requer dados específicos do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f95f9-108">The integration requires specific data from Human Resources.</span></span> <span data-ttu-id="f95f9-109">Portanto, você deve verificar se os dados mapeados para o Dayforce estão configurados no Human Resources de forma compatível com a integração.</span><span class="sxs-lookup"><span data-stu-id="f95f9-109">Therefore, you must verify that data that is mapped to Dayforce is configured in Human Resources in a manner that supports the integration.</span></span> <span data-ttu-id="f95f9-110">A integração usa as seguintes categorias amplas de dados:</span><span class="sxs-lookup"><span data-stu-id="f95f9-110">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="f95f9-111">Dados de recursos humanos</span><span class="sxs-lookup"><span data-stu-id="f95f9-111">Human resources data</span></span>
- <span data-ttu-id="f95f9-112">Dados de remuneração</span><span class="sxs-lookup"><span data-stu-id="f95f9-112">Compensation data</span></span>
- <span data-ttu-id="f95f9-113">Dados da folha de pagamento, como ciclos de pagamento, períodos de pagamento e códigos de ganhos</span><span class="sxs-lookup"><span data-stu-id="f95f9-113">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="f95f9-114">Dados do trabalhador</span><span class="sxs-lookup"><span data-stu-id="f95f9-114">Worker data</span></span>

<span data-ttu-id="f95f9-115">Este artigo descreve as etapas que você deve seguir para ativar a integração.</span><span class="sxs-lookup"><span data-stu-id="f95f9-115">This article describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="f95f9-116">Também explica os tipos de dados e os detalhes de configuração que a integração requer.</span><span class="sxs-lookup"><span data-stu-id="f95f9-116">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="f95f9-117">Habilitar a integração</span><span class="sxs-lookup"><span data-stu-id="f95f9-117">Enable the integration</span></span>

<span data-ttu-id="f95f9-118">No Human Resources, você deve ativar a integração e inserir as informações de configuração para se conectar ao Dayforce.</span><span class="sxs-lookup"><span data-stu-id="f95f9-118">In Human Resources, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="f95f9-119">Para que a transação de contabilidade produzida seja importada para o Microsoft Dynamics 365 Finance, também é preciso configurar uma conta de armazenamento do Microsoft Azure e inserir a cadeia de conexão do Armazenamento do Azure no Finance.</span><span class="sxs-lookup"><span data-stu-id="f95f9-119">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 Finance, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance.</span></span>

<span data-ttu-id="f95f9-120">Para ativar a integração no Human Resources, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="f95f9-120">To turn on the integration in Human Resources, follow these steps.</span></span>

1. <span data-ttu-id="f95f9-121">Na página **Administração do sistema**, selecione **Configuração de integração**.</span><span class="sxs-lookup"><span data-stu-id="f95f9-121">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="f95f9-122">Digite o ponto de extremidade seguro do File Transfer Protocol (FTP) e o caminho seguro da pasta FTP.</span><span class="sxs-lookup"><span data-stu-id="f95f9-122">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="f95f9-123">Digite o nome e a senha do usuário que acessará o ponto de extremidade e o caminho da pasta seguros do FTP.</span><span class="sxs-lookup"><span data-stu-id="f95f9-123">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="f95f9-124">Teste a conexão, conforme necessário, e defina a opção **Habilitar integração da folha de pagamento** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="f95f9-124">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="f95f9-125">Quando a integração é ativada, o pacote e os arquivos de exportação de dados são criados e a frequência é configurada.</span><span class="sxs-lookup"><span data-stu-id="f95f9-125">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="f95f9-126">Você pode alterar essa frequência conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="f95f9-126">You can change this frequency as you require.</span></span>

<span data-ttu-id="f95f9-127">Para obter mais informações sobre as contas de armazenamento do Azure e as cadeias de conexão do Armazenamento do Azure, consulte os seguintes artigos do Azure:</span><span class="sxs-lookup"><span data-stu-id="f95f9-127">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure articles:</span></span>

- [<span data-ttu-id="f95f9-128">Sobre as contas de armazenamento do Azure</span><span class="sxs-lookup"><span data-stu-id="f95f9-128">About Azure storage accounts</span></span>](/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="f95f9-129">Configurar cadeias de conexão do Armazenamento do Azure</span><span class="sxs-lookup"><span data-stu-id="f95f9-129">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)

### <a name="technical-details-when-payroll-integration-is-enabled"></a><span data-ttu-id="f95f9-130">Detalhes técnicos quando a integração da folha de pagamento está habilitada</span><span class="sxs-lookup"><span data-stu-id="f95f9-130">Technical details when payroll integration is enabled</span></span>

<span data-ttu-id="f95f9-131">A ativação da integração da folha de pagamento tem dois efeitos principais:</span><span class="sxs-lookup"><span data-stu-id="f95f9-131">Turning on the payroll integration has two primary effects:</span></span>

- <span data-ttu-id="f95f9-132">Um projeto de exportação de dados denominado "Exportação de integração da folha de pagamento" é criado.</span><span class="sxs-lookup"><span data-stu-id="f95f9-132">A data export project named "Payroll integration export" is created.</span></span> <span data-ttu-id="f95f9-133">Este projeto contém as entidades e os campos necessários para a integração da folha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="f95f9-133">This project contains the entities and fields required for the payroll integration.</span></span> <span data-ttu-id="f95f9-134">Para revisar o projeto, vá para **Administração do sistema**, selecione o bloco **Gerenciamento de dados** e abra o projeto de dados da lista de projetos.</span><span class="sxs-lookup"><span data-stu-id="f95f9-134">To examine the project, go to **System administration**, select the **Data management** tile, and then open the data project from the list of projects.</span></span>
- <span data-ttu-id="f95f9-135">Esse trabalho em lotes executa o projeto de exportação de dados, criptografa o pacote de dados resultante e transfere o arquivo do pacote de dados para a empresa de SFTP configurada na tela **Configuração de integração**.</span><span class="sxs-lookup"><span data-stu-id="f95f9-135">This batch job executes the data export project, encrypts the resulting data package, and transfers the data package file to the SFTP endpoint configured on the **Integration configuration** screen.</span></span>

> [!NOTE]
> <span data-ttu-id="f95f9-136">O pacote de dados transferido para a empresa de SFTP é criptografado usando uma chave exclusiva para o pacote.</span><span class="sxs-lookup"><span data-stu-id="f95f9-136">The data package transferred to the SFTP endpoint is encrypted using a key that is unique to the package.</span></span> <span data-ttu-id="f95f9-137">A chave é um Azure Key Vault acessível somente pelo Ceridian.</span><span class="sxs-lookup"><span data-stu-id="f95f9-137">The key is in an Azure Key Vault that is accessible only by Ceridian.</span></span> <span data-ttu-id="f95f9-138">Não é possível descriptografar e revisar o conteúdo do pacote de dados.</span><span class="sxs-lookup"><span data-stu-id="f95f9-138">It is not possible to decrypt and examine the data package contents.</span></span> <span data-ttu-id="f95f9-139">Se você precisar examinar o conteúdo do pacote de dados, exporte manualmente o projeto de dados "Exportação de integração da folha de pagamento", baixe-o e abra-o</span><span class="sxs-lookup"><span data-stu-id="f95f9-139">If you need to examine the contents of the data package, you need to export the "Payroll integration export" data project manually, download it, and then open it.</span></span> <span data-ttu-id="f95f9-140">A exportação manual não aplicará a criptografia nem transferirá o pacote.</span><span class="sxs-lookup"><span data-stu-id="f95f9-140">Manual export will not apply encryption or transfer the package.</span></span>
> <span data-ttu-id="f95f9-141">Para instâncias em que os arquivos de integração são enviados de um ambiente de UAT ou de área restrita do Dynamics 365 Human Resources para um ambiente de teste Ceridian Dayforce, você pode usar a seguinte URL do cofre de chaves: https://payrollintegrationprod.vault.azure.net.</span><span class="sxs-lookup"><span data-stu-id="f95f9-141">For instances where the integration files are sent from a Dynamics 365 Human Resources UAT or Sandbox environment to a Ceridian Dayforce Test environment, you can use the following key vault URL: https://payrollintegrationprod.vault.azure.net.</span></span>

## <a name="configure-your-data"></a><span data-ttu-id="f95f9-142">Configurar seus dados</span><span class="sxs-lookup"><span data-stu-id="f95f9-142">Configure your data</span></span> 

<span data-ttu-id="f95f9-143">Para processar a folha de pagamento, você deve configurar dados de RH no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f95f9-143">To process payroll, you must configure human resource data in Human Resources.</span></span> <span data-ttu-id="f95f9-144">Você deve configurar dados organizacionais, como cargos e posições, juntamente com informações sobre benefícios e remuneração.</span><span class="sxs-lookup"><span data-stu-id="f95f9-144">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="f95f9-145">Esses dados fornecem as informações de emprego, pagamento e dedução necessárias para gerar o pagamento do empregado.</span><span class="sxs-lookup"><span data-stu-id="f95f9-145">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="f95f9-146">Dados de RH</span><span class="sxs-lookup"><span data-stu-id="f95f9-146">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="f95f9-147">Benefícios</span><span class="sxs-lookup"><span data-stu-id="f95f9-147">Benefits</span></span> 

<span data-ttu-id="f95f9-148">O RH fornece ferramentas para a configuração e manutenção dos benefícios, deduções e planos de remuneração do trabalhador que uma organização oferece ou processa para seus funcionários.</span><span class="sxs-lookup"><span data-stu-id="f95f9-148">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="f95f9-149">Ao criar benefícios, tenha em mente os dados e configurações a seguir usados no Dayforce.</span><span class="sxs-lookup"><span data-stu-id="f95f9-149">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="f95f9-150">Planos de benefícios</span><span class="sxs-lookup"><span data-stu-id="f95f9-150">Benefit plans</span></span>

- <span data-ttu-id="f95f9-151">Plano (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-151">Plan (required)</span></span>
- <span data-ttu-id="f95f9-152">Tipo (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-152">Type (required)</span></span>
- <span data-ttu-id="f95f9-153">Impacto da folha de pagamento (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-153">Payroll impact (required)</span></span>
- <span data-ttu-id="f95f9-154">Recuperar atrasos de pagamento</span><span class="sxs-lookup"><span data-stu-id="f95f9-154">Recover arrears</span></span>
- <span data-ttu-id="f95f9-155">Método de dedução</span><span class="sxs-lookup"><span data-stu-id="f95f9-155">Deduction method</span></span>
- <span data-ttu-id="f95f9-156">Prioridade da dedução</span><span class="sxs-lookup"><span data-stu-id="f95f9-156">Deduction priority</span></span>
- <span data-ttu-id="f95f9-157">Limitar período</span><span class="sxs-lookup"><span data-stu-id="f95f9-157">Limit period</span></span>
- <span data-ttu-id="f95f9-158">Valor de limite</span><span class="sxs-lookup"><span data-stu-id="f95f9-158">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="f95f9-159">Benefícios</span><span class="sxs-lookup"><span data-stu-id="f95f9-159">Benefits</span></span>

- <span data-ttu-id="f95f9-160">Plano (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-160">Plan (required)</span></span>
- <span data-ttu-id="f95f9-161">Tipo (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-161">Type (required)</span></span>
- <span data-ttu-id="f95f9-162">Opção (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="f95f9-162">Option (required)</span></span>
- <span data-ttu-id="f95f9-163">ID do benefício (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="f95f9-163">Benefit ID (required)</span></span>
- <span data-ttu-id="f95f9-164">Frequência</span><span class="sxs-lookup"><span data-stu-id="f95f9-164">Frequency</span></span>
- <span data-ttu-id="f95f9-165">Base</span><span class="sxs-lookup"><span data-stu-id="f95f9-165">Basis</span></span>
- <span data-ttu-id="f95f9-166">Valor ou taxa</span><span class="sxs-lookup"><span data-stu-id="f95f9-166">Amount or rate</span></span>
- <span data-ttu-id="f95f9-167">Código de ganhos</span><span class="sxs-lookup"><span data-stu-id="f95f9-167">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="f95f9-168">Frequências com suporte</span><span class="sxs-lookup"><span data-stu-id="f95f9-168">Supported frequencies</span></span> 

- <span data-ttu-id="f95f9-169">Semanalmente</span><span class="sxs-lookup"><span data-stu-id="f95f9-169">Weekly</span></span>
- <span data-ttu-id="f95f9-170">Por quinzena</span><span class="sxs-lookup"><span data-stu-id="f95f9-170">Bi-weekly</span></span>
- <span data-ttu-id="f95f9-171">Quinzenal</span><span class="sxs-lookup"><span data-stu-id="f95f9-171">Semi-monthly</span></span>
- <span data-ttu-id="f95f9-172">Mensalmente</span><span class="sxs-lookup"><span data-stu-id="f95f9-172">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="f95f9-173">Bases com suporte</span><span class="sxs-lookup"><span data-stu-id="f95f9-173">Supported bases</span></span> 

- <span data-ttu-id="f95f9-174">Valor fixo</span><span class="sxs-lookup"><span data-stu-id="f95f9-174">Fixed amount</span></span>
- <span data-ttu-id="f95f9-175">Percentual de ganhos</span><span class="sxs-lookup"><span data-stu-id="f95f9-175">Percent of earnings</span></span>
- <span data-ttu-id="f95f9-176">Horas produtivas</span><span class="sxs-lookup"><span data-stu-id="f95f9-176">Productive hours</span></span>

<span data-ttu-id="f95f9-177">O Dayforce cria as deduções a seguir, com base no impacto da folha de pagamento definido no plano de benefícios.</span><span class="sxs-lookup"><span data-stu-id="f95f9-177">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="f95f9-178">Seleção no Human Resources</span><span class="sxs-lookup"><span data-stu-id="f95f9-178">Selection in Human Resources</span></span>        | <span data-ttu-id="f95f9-179">Resultado no Dayforce</span><span class="sxs-lookup"><span data-stu-id="f95f9-179">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="f95f9-180">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="f95f9-180">None</span></span>                       | <span data-ttu-id="f95f9-181">Nenhuma dedução é criada.</span><span class="sxs-lookup"><span data-stu-id="f95f9-181">No deduction is created.</span></span>                      |
| <span data-ttu-id="f95f9-182">Somente dedução</span><span class="sxs-lookup"><span data-stu-id="f95f9-182">Deduction only</span></span>             | <span data-ttu-id="f95f9-183">Uma dedução de funcionário é criada.</span><span class="sxs-lookup"><span data-stu-id="f95f9-183">An employee deduction is created.</span></span>             |
| <span data-ttu-id="f95f9-184">Somente contribuição</span><span class="sxs-lookup"><span data-stu-id="f95f9-184">Contribution only</span></span>          | <span data-ttu-id="f95f9-185">Uma dedução de empregador é criada.</span><span class="sxs-lookup"><span data-stu-id="f95f9-185">An employer deduction is created.</span></span>             |
| <span data-ttu-id="f95f9-186">Dedução e contribuição</span><span class="sxs-lookup"><span data-stu-id="f95f9-186">Deduction and contribution</span></span> | <span data-ttu-id="f95f9-187">Deduções de funcionário e empregador são criadas.</span><span class="sxs-lookup"><span data-stu-id="f95f9-187">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="f95f9-188">Para obter mais informações sobre como definir e gerenciar um programa de benefícios, consulte os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="f95f9-188">For more information about how to define and manage a benefits program, see the following articles:</span></span>

- [<span data-ttu-id="f95f9-189">Entregar um programa de benefícios para funcionários</span><span class="sxs-lookup"><span data-stu-id="f95f9-189">Deliver an employee benefits program</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="f95f9-190">Criar um novo benefício</span><span class="sxs-lookup"><span data-stu-id="f95f9-190">Create a new benefit</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="f95f9-191">Definir regras e políticas de qualificação para o benefício</span><span class="sxs-lookup"><span data-stu-id="f95f9-191">Define benefit eligibility rules and policies</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="f95f9-192">Inscrever e remover benefícios de trabalhadores</span><span class="sxs-lookup"><span data-stu-id="f95f9-192">Enroll and remove benefits from workers</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="f95f9-193">Remuneração</span><span class="sxs-lookup"><span data-stu-id="f95f9-193">Compensation</span></span> 

<span data-ttu-id="f95f9-194">O gerenciamento de remuneração é usado para controlar o pagamento do salário base e de prêmios.</span><span class="sxs-lookup"><span data-stu-id="f95f9-194">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="f95f9-195">Os aumentos no salário base fixo e nos prêmios de um funcionário são controlados por meio de planos de remuneração fixos.</span><span class="sxs-lookup"><span data-stu-id="f95f9-195">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="f95f9-196">O pagamento de incentivos, como pagamentos de bônus, prêmios por desempenho, opções de ação e concessões, além de prêmios únicos, são controlados por meio de planos de remuneração variável.</span><span class="sxs-lookup"><span data-stu-id="f95f9-196">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="f95f9-197">O Dayforce usa informações de remuneração para calcular a taxa por hora ou anual de um funcionário.</span><span class="sxs-lookup"><span data-stu-id="f95f9-197">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="f95f9-198">Planos de remuneração fixa e conversões de taxa de pagamento são necessários.</span><span class="sxs-lookup"><span data-stu-id="f95f9-198">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="f95f9-199">Os funcionários devem estar associados a um plano de remuneração fixa.</span><span class="sxs-lookup"><span data-stu-id="f95f9-199">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="f95f9-200">Para obter mais informações sobre planos de compensação, veja os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="f95f9-200">For more information about compensation plans, see the following articles:</span></span>

- [<span data-ttu-id="f95f9-201">Criar planos de remuneração fixa</span><span class="sxs-lookup"><span data-stu-id="f95f9-201">Create fixed compensation plans</span></span>](/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="f95f9-202">Criar planos de remuneração variável</span><span class="sxs-lookup"><span data-stu-id="f95f9-202">Create variable compensation plans</span></span>](/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="f95f9-203">Desenvolver estrutura e planos de remuneração/salário</span><span class="sxs-lookup"><span data-stu-id="f95f9-203">Develop salary/compensation structure and plans</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="f95f9-204">Processar remuneração</span><span class="sxs-lookup"><span data-stu-id="f95f9-204">Process compensation</span></span>](/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="f95f9-205">Definir processo de remuneração e calcular resultados</span><span class="sxs-lookup"><span data-stu-id="f95f9-205">Define compensation process and calculate results</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="f95f9-206">Inscrever um funcionário em um plano de remuneração fixa</span><span class="sxs-lookup"><span data-stu-id="f95f9-206">Enroll an employee in a fixed compensation plan</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="f95f9-207">Inscrever um funcionário em um plano de remuneração variável</span><span class="sxs-lookup"><span data-stu-id="f95f9-207">Enroll an employee in a variable compensation plan</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="f95f9-208">Trabalhos</span><span class="sxs-lookup"><span data-stu-id="f95f9-208">Jobs</span></span> 

<span data-ttu-id="f95f9-209">Um trabalho é um conjunto de tarefas e responsabilidades exigidas de uma pessoa que realiza um trabalho.</span><span class="sxs-lookup"><span data-stu-id="f95f9-209">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="f95f9-210">Para obter mais informações, consulte os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="f95f9-210">For more information, see the following articles:</span></span>

- [<span data-ttu-id="f95f9-211">Configurando os componentes de um trabalho</span><span class="sxs-lookup"><span data-stu-id="f95f9-211">Setting up the components of a job</span></span>](/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="f95f9-212">Definir novos trabalhos</span><span class="sxs-lookup"><span data-stu-id="f95f9-212">Define new jobs</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="f95f9-213">Cargos</span><span class="sxs-lookup"><span data-stu-id="f95f9-213">Positions</span></span>

<span data-ttu-id="f95f9-214">Um cargo é uma instância individual de um trabalho.</span><span class="sxs-lookup"><span data-stu-id="f95f9-214">A position is an individual instance of a job.</span></span> <span data-ttu-id="f95f9-215">Por exemplo, a posição "Gerente de vendas (Leste)" é uma das posições associadas ao trabalho "Gerente de vendas".</span><span class="sxs-lookup"><span data-stu-id="f95f9-215">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="f95f9-216">Uma posição existe em um departamento.</span><span class="sxs-lookup"><span data-stu-id="f95f9-216">A position exists in a department.</span></span> <span data-ttu-id="f95f9-217">Apenas um trabalhador pode ser associado a cada posição.</span><span class="sxs-lookup"><span data-stu-id="f95f9-217">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="f95f9-218">Considere os seguintes dados e configurações ao configurar as posições:</span><span class="sxs-lookup"><span data-stu-id="f95f9-218">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="f95f9-219">Posição (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="f95f9-219">Position (required)</span></span>
- <span data-ttu-id="f95f9-220">Descrição (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="f95f9-220">Description (required)</span></span>
- <span data-ttu-id="f95f9-221">Trabalho (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-221">Job (required)</span></span>
- <span data-ttu-id="f95f9-222">Departamento (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-222">Department (required)</span></span>
- <span data-ttu-id="f95f9-223">Tipo de posição (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-223">Position type (required)</span></span>
- <span data-ttu-id="f95f9-224">Equivalente ao horário integral</span><span class="sxs-lookup"><span data-stu-id="f95f9-224">Full-time equivalent</span></span>
- <span data-ttu-id="f95f9-225">Horas normais anuais (obrigatórias)</span><span class="sxs-lookup"><span data-stu-id="f95f9-225">Annual regular hours (required)</span></span>
- <span data-ttu-id="f95f9-226">Pago por entidade legal (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-226">Paid by legal entity (required)</span></span>
- <span data-ttu-id="f95f9-227">Ciclo de pagamento (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-227">Pay cycle (required)</span></span>
- <span data-ttu-id="f95f9-228">Dimensão financeira padrão – Centro de custo (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-228">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="f95f9-229">Atribuição do trabalhador – Trabalhador, início da atribuição, fim da atribuição, código de motivo</span><span class="sxs-lookup"><span data-stu-id="f95f9-229">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="f95f9-230">Se várias posições no mesmo departamento estiverem associadas ao mesmo trabalho, elas serão consolidadas em uma única posição no Dayforce.</span><span class="sxs-lookup"><span data-stu-id="f95f9-230">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="f95f9-231">Para obter mais informações, consulte os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="f95f9-231">For more information, see the following articles:</span></span>

- [<span data-ttu-id="f95f9-232">Organizar sua força de trabalho usando departamentos, trabalhos e posições</span><span class="sxs-lookup"><span data-stu-id="f95f9-232">Organize your workforce using departments, jobs, and positions</span></span>](/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="f95f9-233">Configurar posições</span><span class="sxs-lookup"><span data-stu-id="f95f9-233">Set up positions</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="f95f9-234">Departamentos</span><span class="sxs-lookup"><span data-stu-id="f95f9-234">Departments</span></span>

<span data-ttu-id="f95f9-235">Um departamento é uma unidade operacional que representa uma categoria ou uma área funcional de uma organização.</span><span class="sxs-lookup"><span data-stu-id="f95f9-235">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="f95f9-236">Um departamento é responsável por uma área específica da organização, como vendas, contabilidade ou recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="f95f9-236">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="f95f9-237">Você pode usar departamentos para relatar áreas funcionais.</span><span class="sxs-lookup"><span data-stu-id="f95f9-237">You can use departments to report on functional areas.</span></span> <span data-ttu-id="f95f9-238">Os departamentos podem ter a responsabilidade de lucros e perdas.</span><span class="sxs-lookup"><span data-stu-id="f95f9-238">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="f95f9-239">Para obter mais informações, consulte os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="f95f9-239">For more information, see the following articles:</span></span>

- [<span data-ttu-id="f95f9-240">Criar um departamento e associá-lo à hierarquia de departamentos</span><span class="sxs-lookup"><span data-stu-id="f95f9-240">Create a department and associate it with the department hierarchy</span></span>](/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="f95f9-241">Definir novos departamentos</span><span class="sxs-lookup"><span data-stu-id="f95f9-241">Define new departments</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="f95f9-242">Ciclos de pagamento e períodos de pagamento</span><span class="sxs-lookup"><span data-stu-id="f95f9-242">Pay cycles and pay periods</span></span>

<span data-ttu-id="f95f9-243">Um ciclo de pagamento determina a frequência com que a folha de pagamento é executada e os dias específicos em que os trabalhadores são pagos.</span><span class="sxs-lookup"><span data-stu-id="f95f9-243">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="f95f9-244">Por exemplo, um ciclo de pagamento pode ser mensal e os funcionários podem ser pagos no último dia do mês.</span><span class="sxs-lookup"><span data-stu-id="f95f9-244">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="f95f9-245">Como alternativa, um ciclo de pagamento pode ser semanal e os funcionários podem ser pagos na terça-feira após o término do período de pagamento.</span><span class="sxs-lookup"><span data-stu-id="f95f9-245">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="f95f9-246">Ciclos de pagamento são atribuídos a posições para controlar quando os trabalhadores nessas posições são pagos.</span><span class="sxs-lookup"><span data-stu-id="f95f9-246">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="f95f9-247">Após a criação dos ciclos de pagamento, você pode gerar períodos de pagamento para cada ciclo.</span><span class="sxs-lookup"><span data-stu-id="f95f9-247">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="f95f9-248">Cada período de pagamento inclui uma data de pagamento padrão baseada nas informações que você fornece.</span><span class="sxs-lookup"><span data-stu-id="f95f9-248">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="f95f9-249">No entanto, você pode modificar a data de pagamento padrão em um período de pagamento para permitir exceções (por exemplo, quando a data de pagamento cai em um feriado).</span><span class="sxs-lookup"><span data-stu-id="f95f9-249">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="f95f9-250">As seguintes informações são usadas no Dayforce:</span><span class="sxs-lookup"><span data-stu-id="f95f9-250">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="f95f9-251">Ciclo de pagamento (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-251">Pay cycle (required)</span></span>
- <span data-ttu-id="f95f9-252">Frequência do ciclo de pagamento (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="f95f9-252">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="f95f9-253">Data de início do período (primeiro período de pagamento obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-253">Period start date (first pay period required)</span></span>
- <span data-ttu-id="f95f9-254">Data de pagamento padrão (primeiro período de pagamento obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-254">Default payment date (first pay period required)</span></span>

<span data-ttu-id="f95f9-255">Essas informações são integradas ao Dayforce como grupos de pagamento e são separadas por país ou região para cada ciclo de pagamento.</span><span class="sxs-lookup"><span data-stu-id="f95f9-255">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="f95f9-256">Pelo menos um período de pagamento deve ser gerado antes da integração.</span><span class="sxs-lookup"><span data-stu-id="f95f9-256">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="f95f9-257">O Dayforce gera datas de pagamento e calendários do grupo de pagamento, com base na data de início do primeiro período de pagamento e na data de pagamento padrão configurada no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f95f9-257">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Human Resources.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="f95f9-258">Códigos de ganhos</span><span class="sxs-lookup"><span data-stu-id="f95f9-258">Earning codes</span></span>

<span data-ttu-id="f95f9-259">Os códigos de ganhos identificam de forma exclusiva cada tipo de ganho que os trabalhadores recebem.</span><span class="sxs-lookup"><span data-stu-id="f95f9-259">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="f95f9-260">Os códigos têm vários parâmetros relacionados a ganhos, como regras contábeis, leis tributárias, requisitos de relatório e capacidade de montante bruto.</span><span class="sxs-lookup"><span data-stu-id="f95f9-260">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="f95f9-261">As seguintes informações são usadas no Dayforce:</span><span class="sxs-lookup"><span data-stu-id="f95f9-261">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="f95f9-262">Código de ganhos (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-262">Earning Code (required)</span></span>
- <span data-ttu-id="f95f9-263">descrição</span><span class="sxs-lookup"><span data-stu-id="f95f9-263">Description</span></span>
- <span data-ttu-id="f95f9-264">Unidade de medida</span><span class="sxs-lookup"><span data-stu-id="f95f9-264">Unit of measure</span></span>
- <span data-ttu-id="f95f9-265">Produtivo</span><span class="sxs-lookup"><span data-stu-id="f95f9-265">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="f95f9-266">Dados do trabalhador</span><span class="sxs-lookup"><span data-stu-id="f95f9-266">Worker data</span></span>

<span data-ttu-id="f95f9-267">Os registros dos vários tipos de trabalhadores que você tem são importantes para o RH e sistemas de folha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="f95f9-267">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="f95f9-268">As informações inseridas podem ser usadas para rastrear trabalhadores e informações pessoais.</span><span class="sxs-lookup"><span data-stu-id="f95f9-268">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="f95f9-269">Você pode manter estas informações para trabalhadores:</span><span class="sxs-lookup"><span data-stu-id="f95f9-269">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="f95f9-270">**Básicas** – mantenha informações básicas do trabalhador, como informações de contato, demográficas, de identificação, sobre a família, o status de serviço militar, informações de exilado, contatos pessoais e de emergência.</span><span class="sxs-lookup"><span data-stu-id="f95f9-270">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="f95f9-271">**Emprego** – mantenha informações sobre o emprego dos trabalhadores, como a afiliação da empresa ou organização, a atribuição de posição, as datas inicial e final, a qualificação para trabalho, o contrato de trabalho, a pensão, férias e as informações de mudança.</span><span class="sxs-lookup"><span data-stu-id="f95f9-271">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="f95f9-272">**Licença e ausência** – mantenha informações sobre as ausências dos trabalhadores, como o calendário de trabalho, as transações de ausência e a configuração de ausência.</span><span class="sxs-lookup"><span data-stu-id="f95f9-272">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="f95f9-273">**Remuneração e folha de pagamento** – mantenha informações sobre os planos de remuneração e as informações de folha de pagamento de trabalhadores, como o registro do plano, prêmios, o desempenho, a comissão, informações sobre impostos, aposentadoria e deduções do salário.</span><span class="sxs-lookup"><span data-stu-id="f95f9-273">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="f95f9-274">Ao inserir informações do trabalhador, tenha em mente os dados e configurações a seguir usados no Dayforce.</span><span class="sxs-lookup"><span data-stu-id="f95f9-274">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="f95f9-275">Informações gerais</span><span class="sxs-lookup"><span data-stu-id="f95f9-275">General information</span></span>

- <span data-ttu-id="f95f9-276">Número de equipe (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-276">Personnel number (required)</span></span>
- <span data-ttu-id="f95f9-277">Nome (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-277">First name (required)</span></span>
- <span data-ttu-id="f95f9-278">Sobrenome (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-278">Last name (required)</span></span>
- <span data-ttu-id="f95f9-279">Nome do meio</span><span class="sxs-lookup"><span data-stu-id="f95f9-279">Middle name</span></span>
- <span data-ttu-id="f95f9-280">Aniversário de tempo de serviço</span><span class="sxs-lookup"><span data-stu-id="f95f9-280">Seniority date</span></span>
- <span data-ttu-id="f95f9-281">Conhecido como</span><span class="sxs-lookup"><span data-stu-id="f95f9-281">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="f95f9-282">Informações pessoais</span><span class="sxs-lookup"><span data-stu-id="f95f9-282">Personal information</span></span>

- <span data-ttu-id="f95f9-283">Estado civil (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-283">Marital status (required)</span></span>
- <span data-ttu-id="f95f9-284">Data de nascimento (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="f95f9-284">Birth date (required)</span></span>
- <span data-ttu-id="f95f9-285">Sexo (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-285">Gender (required)</span></span>
- <span data-ttu-id="f95f9-286">Pessoa portadora de deficiências</span><span class="sxs-lookup"><span data-stu-id="f95f9-286">Person with disabilities</span></span>
- <span data-ttu-id="f95f9-287">Região do país de nacionalidade (somente para o México)</span><span class="sxs-lookup"><span data-stu-id="f95f9-287">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="f95f9-288">Informações de endereço</span><span class="sxs-lookup"><span data-stu-id="f95f9-288">Address information</span></span>

- <span data-ttu-id="f95f9-289">Principal (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-289">Primary (required)</span></span>
- <span data-ttu-id="f95f9-290">País/região (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-290">Country/region (required)</span></span>
- <span data-ttu-id="f95f9-291">CEP (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-291">Postal code (required)</span></span>
- <span data-ttu-id="f95f9-292">Número da rua (obrigatório) (somente para o México)</span><span class="sxs-lookup"><span data-stu-id="f95f9-292">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="f95f9-293">Complemento do edifício (somente para o México)</span><span class="sxs-lookup"><span data-stu-id="f95f9-293">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="f95f9-294">Cidade (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="f95f9-294">City (required)</span></span>
- <span data-ttu-id="f95f9-295">Estado (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-295">State (required)</span></span>
- <span data-ttu-id="f95f9-296">Município (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-296">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="f95f9-297">Informações de contato</span><span class="sxs-lookup"><span data-stu-id="f95f9-297">Contact information</span></span> 

- <span data-ttu-id="f95f9-298">Principal (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-298">Primary (required)</span></span>
- <span data-ttu-id="f95f9-299">Número de contato (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-299">Contact number (required)</span></span>
- <span data-ttu-id="f95f9-300">Extensão</span><span class="sxs-lookup"><span data-stu-id="f95f9-300">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="f95f9-301">Informações sobre folha de pagamento e códigos de ganhos</span><span class="sxs-lookup"><span data-stu-id="f95f9-301">Payroll information and earning codes</span></span>

<span data-ttu-id="f95f9-302">Os funcionários podem receber ganhos específicos com uma determinada frequência de pagamento e ter um método de pagamento preferencial.</span><span class="sxs-lookup"><span data-stu-id="f95f9-302">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="f95f9-303">Os campos a seguir são usados no Dayforce para ajudar a garantir que essas preferências e configurações sejam usadas.</span><span class="sxs-lookup"><span data-stu-id="f95f9-303">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="f95f9-304">Códigos de ganhos</span><span class="sxs-lookup"><span data-stu-id="f95f9-304">Earning codes</span></span>

- <span data-ttu-id="f95f9-305">Posição (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="f95f9-305">Position (required)</span></span>
- <span data-ttu-id="f95f9-306">Código de ganhos (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-306">Earning Code (required)</span></span>
- <span data-ttu-id="f95f9-307">Frequência (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="f95f9-307">Frequency (required)</span></span>
- <span data-ttu-id="f95f9-308">Valor (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-308">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="f95f9-309">Informações da folha de pagamento</span><span class="sxs-lookup"><span data-stu-id="f95f9-309">Payroll information</span></span>

- <span data-ttu-id="f95f9-310">Método de Pagamento</span><span class="sxs-lookup"><span data-stu-id="f95f9-310">Payment Method</span></span>
- <span data-ttu-id="f95f9-311">Região econômica (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="f95f9-311">Economic Region (required)</span></span>
- <span data-ttu-id="f95f9-312">ID de Benefícios do Funcionário</span><span class="sxs-lookup"><span data-stu-id="f95f9-312">Employee Benefits ID</span></span>
- <span data-ttu-id="f95f9-313">Número de ID nacional (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-313">National ID Number (required)</span></span>
- <span data-ttu-id="f95f9-314">Número de serviço militar</span><span class="sxs-lookup"><span data-stu-id="f95f9-314">Military Service Number</span></span>
- <span data-ttu-id="f95f9-315">ID de turno (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="f95f9-315">Shift ID (required)</span></span>
- <span data-ttu-id="f95f9-316">Número fiscal (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-316">Tax Number (required)</span></span>
- <span data-ttu-id="f95f9-317">ID do sindicato (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="f95f9-317">Union ID (required)</span></span>
- <span data-ttu-id="f95f9-318">ID do dia útil (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="f95f9-318">Work Day ID (required)</span></span>
- <span data-ttu-id="f95f9-319">Número de autorização de trabalho</span><span class="sxs-lookup"><span data-stu-id="f95f9-319">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="f95f9-320">Para o método de pagamento, o México permite **Pagamento à vista**, **Cheque** (o cheque físico da empresa) e **Pagamento Eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="f95f9-320">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="f95f9-321">Se nenhum método de pagamento for especificado, **Cheque** é usado por padrão.</span><span class="sxs-lookup"><span data-stu-id="f95f9-321">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="f95f9-322">Detalhes do emprego</span><span class="sxs-lookup"><span data-stu-id="f95f9-322">Employment details</span></span>

<span data-ttu-id="f95f9-323">O histórico de detalhes de emprego é usado como principal informação para derivar os status de contratação, rescisão e recontratação de um funcionário no Dayforce.</span><span class="sxs-lookup"><span data-stu-id="f95f9-323">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="f95f9-324">O Dayforce suporta apenas um registro de emprego ativo de cada vez.</span><span class="sxs-lookup"><span data-stu-id="f95f9-324">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="f95f9-325">Data de início do emprego (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="f95f9-325">Employment start date (required)</span></span>
- <span data-ttu-id="f95f9-326">Data final do emprego</span><span class="sxs-lookup"><span data-stu-id="f95f9-326">Employment end date</span></span>
- <span data-ttu-id="f95f9-327">Data de início</span><span class="sxs-lookup"><span data-stu-id="f95f9-327">Start date</span></span>
- <span data-ttu-id="f95f9-328">Data inicial ajustada</span><span class="sxs-lookup"><span data-stu-id="f95f9-328">Adjusted start date</span></span>
- <span data-ttu-id="f95f9-329">Data de rescisão (obrigatória após a rescisão)</span><span class="sxs-lookup"><span data-stu-id="f95f9-329">Termination date (required upon termination)</span></span>
- <span data-ttu-id="f95f9-330">Motivo da rescisão (obrigatória após a rescisão)</span><span class="sxs-lookup"><span data-stu-id="f95f9-330">Termination reason (required upon termination)</span></span>

<span data-ttu-id="f95f9-331">As principais datas de um funcionário são derivadas usando-se as informações a seguir.</span><span class="sxs-lookup"><span data-stu-id="f95f9-331">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="f95f9-332">Recursos Humanos</span><span class="sxs-lookup"><span data-stu-id="f95f9-332">Human Resources</span></span>                | <span data-ttu-id="f95f9-333">Dayforce</span><span class="sxs-lookup"><span data-stu-id="f95f9-333">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="f95f9-334">Data de contratação mais recente</span><span class="sxs-lookup"><span data-stu-id="f95f9-334">Most recent hire date</span></span> | <span data-ttu-id="f95f9-335">Início de emprego do registro histórico de emprego atual não terminado</span><span class="sxs-lookup"><span data-stu-id="f95f9-335">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="f95f9-336">Data da rescisão</span><span class="sxs-lookup"><span data-stu-id="f95f9-336">Termination date</span></span>      | <span data-ttu-id="f95f9-337">Data de rescisão do registro histórico de emprego atual não terminado</span><span class="sxs-lookup"><span data-stu-id="f95f9-337">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="f95f9-338">Data de início</span><span class="sxs-lookup"><span data-stu-id="f95f9-338">Start date</span></span>            | <span data-ttu-id="f95f9-339">Data de início ajustada, data de início ou início de emprego do registro histórico de emprego não ativo atual</span><span class="sxs-lookup"><span data-stu-id="f95f9-339">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="f95f9-340">Data original de contratação</span><span class="sxs-lookup"><span data-stu-id="f95f9-340">Original hire date</span></span>    | <span data-ttu-id="f95f9-341">Início de emprego do registro histórico de emprego mais antigo</span><span class="sxs-lookup"><span data-stu-id="f95f9-341">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="f95f9-342">Remuneração</span><span class="sxs-lookup"><span data-stu-id="f95f9-342">Compensation</span></span>

<span data-ttu-id="f95f9-343">Um plano de remuneração fixa deve estar associado à posição principal de cada funcionário durante um período de emprego.</span><span class="sxs-lookup"><span data-stu-id="f95f9-343">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="f95f9-344">Esse período tem início na data em que o funcionário foi contratado (ou na data de início do emprego) e continua até a rescisão.</span><span class="sxs-lookup"><span data-stu-id="f95f9-344">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="f95f9-345">Data de vigência (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="f95f9-345">Effective Date (required)</span></span>
- <span data-ttu-id="f95f9-346">Data de vencimento</span><span class="sxs-lookup"><span data-stu-id="f95f9-346">Expiration date</span></span>
- <span data-ttu-id="f95f9-347">Taxa de pagamento (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="f95f9-347">Pay Rate (required)</span></span>
- <span data-ttu-id="f95f9-348">Conversões de taxa de pagamento (obrigatórias)</span><span class="sxs-lookup"><span data-stu-id="f95f9-348">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="f95f9-349">Equivalente anual (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-349">Annual equivalent (required)</span></span>
- <span data-ttu-id="f95f9-350">Equivalente por hora (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-350">Hourly equivalent (required)</span></span>

<span data-ttu-id="f95f9-351">Se um funcionário por hora tiver várias posições, a remuneração fixa da posição principal é importada para o Dayforce como a taxa base/salário do nível do funcionário.</span><span class="sxs-lookup"><span data-stu-id="f95f9-351">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="f95f9-352">Para posições não principais, a taxa por hora é salva na posição correspondente no Dayforce.</span><span class="sxs-lookup"><span data-stu-id="f95f9-352">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="f95f9-353">Se um funcionário assalariado tiver várias posições, a taxa acumulada de horas e o salário anual em todas as posições ativas serão derivados e usados como a taxa base/salário do nível do funcionário.</span><span class="sxs-lookup"><span data-stu-id="f95f9-353">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="f95f9-354">Números de identificação</span><span class="sxs-lookup"><span data-stu-id="f95f9-354">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="f95f9-355">Cadastro de Pessoa Física (CPF)</span><span class="sxs-lookup"><span data-stu-id="f95f9-355">Social Security identifier</span></span> 

<span data-ttu-id="f95f9-356">Todos os funcionários devem ter um identificador principal.</span><span class="sxs-lookup"><span data-stu-id="f95f9-356">Every employee must have one primary identifier.</span></span> <span data-ttu-id="f95f9-357">Esse identificador deve ser o tipo de identificação **CPF**.</span><span class="sxs-lookup"><span data-stu-id="f95f9-357">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="f95f9-358">No Dayforce, ele é derivado automaticamente como o identificador de pessoa física do funcionário necessário para a contratação.</span><span class="sxs-lookup"><span data-stu-id="f95f9-358">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="f95f9-359">Principal (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-359">Primary (required)</span></span>
- <span data-ttu-id="f95f9-360">Tipo de identificação = "CPF"</span><span class="sxs-lookup"><span data-stu-id="f95f9-360">Identification Type = "SSN"</span></span>
- <span data-ttu-id="f95f9-361">Data da emissão</span><span class="sxs-lookup"><span data-stu-id="f95f9-361">Issued Date</span></span>
- <span data-ttu-id="f95f9-362">Data de Vencimento</span><span class="sxs-lookup"><span data-stu-id="f95f9-362">Expiration Date</span></span>

<span data-ttu-id="f95f9-363">Os funcionários podem declarar vários números de identificação do tipo de identificação **CPF**.</span><span class="sxs-lookup"><span data-stu-id="f95f9-363">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="f95f9-364">No entanto, somente o registro marcado como **Principal** será integrado ao Dayforce, independentemente de o número estar ativo ou expirado.</span><span class="sxs-lookup"><span data-stu-id="f95f9-364">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="f95f9-365">Contas bancárias e pagamentos</span><span class="sxs-lookup"><span data-stu-id="f95f9-365">Bank accounts and disbursements</span></span>

<span data-ttu-id="f95f9-366">Informações de conta bancária válidas devem ser inseridas para qualquer funcionário que opte por ser pago por meio de transferências bancárias.</span><span class="sxs-lookup"><span data-stu-id="f95f9-366">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="f95f9-367">Recursos Humanos</span><span class="sxs-lookup"><span data-stu-id="f95f9-367">Human Resources</span></span>                         | <span data-ttu-id="f95f9-368">Dayforce</span><span class="sxs-lookup"><span data-stu-id="f95f9-368">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="f95f9-369">Número da conta bancária (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-369">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="f95f9-370">Código SWIFT (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-370">SWIFT code (required)</span></span>          | <span data-ttu-id="f95f9-371">Campo **ID do banco** usado no processamento da folha de pagamento no México.</span><span class="sxs-lookup"><span data-stu-id="f95f9-371">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="f95f9-372">Número da agência (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-372">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="f95f9-373">Tipo de conta bancária (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-373">Bank account type (required)</span></span>   | <span data-ttu-id="f95f9-374">Campo **Tipo de conta** usado no processamento da folha de pagamento no México.</span><span class="sxs-lookup"><span data-stu-id="f95f9-374">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="f95f9-375">Os valores com suporte incluem **Movimento** e **Folha de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="f95f9-375">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="f95f9-376">Os funcionários que optarem por serem pagos por meio de transferências bancárias deverão fornecer um link para uma conta de pendência em uma entidade legal que tenha seu endereço principal no México e esteja associada a uma conta bancária válida de um banco mexicano.</span><span class="sxs-lookup"><span data-stu-id="f95f9-376">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="f95f9-377">Todas as outras contas que não são de pendência são ignoradas.</span><span class="sxs-lookup"><span data-stu-id="f95f9-377">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="f95f9-378">Informações de endereço</span><span class="sxs-lookup"><span data-stu-id="f95f9-378">Address information</span></span>

<span data-ttu-id="f95f9-379">Todos os funcionários devem ter um local principal.</span><span class="sxs-lookup"><span data-stu-id="f95f9-379">Every employee must have one primary location.</span></span> <span data-ttu-id="f95f9-380">No Dayforce, esse local é usado para determinar a residência principal do funcionário para fins fiscais.</span><span class="sxs-lookup"><span data-stu-id="f95f9-380">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="f95f9-381">Principal (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-381">Primary (required)</span></span>
- <span data-ttu-id="f95f9-382">País/região (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-382">Country/region (required)</span></span>
- <span data-ttu-id="f95f9-383">CEP (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-383">Zip/postal code (required)</span></span>
- <span data-ttu-id="f95f9-384">Rua (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="f95f9-384">Street (required)</span></span>
- <span data-ttu-id="f95f9-385">Número da rua (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-385">Street Number (required)</span></span>
- <span data-ttu-id="f95f9-386">Complemento do edifício</span><span class="sxs-lookup"><span data-stu-id="f95f9-386">Building Complement</span></span>
- <span data-ttu-id="f95f9-387">Cidade (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="f95f9-387">City (required)</span></span>
- <span data-ttu-id="f95f9-388">Estado (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-388">State (required)</span></span>
- <span data-ttu-id="f95f9-389">Município (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-389">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="f95f9-390">Configurar seus dados para gerar folha de pagamento nos Estados Unidos e no Canadá</span><span class="sxs-lookup"><span data-stu-id="f95f9-390">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="f95f9-391">Se você está gerando pagamento para funcionários nos Estados Unidos e no Canadá, os seguintes elementos devem ser configurados:</span><span class="sxs-lookup"><span data-stu-id="f95f9-391">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="f95f9-392">Departamentos são necessários em posições.</span><span class="sxs-lookup"><span data-stu-id="f95f9-392">Departments are required on positions.</span></span>
- <span data-ttu-id="f95f9-393">Os centros de custo devem ser definidos como dimensões financeiras e ser o primeiro elemento na sequência de dimensão financeira padrão.</span><span class="sxs-lookup"><span data-stu-id="f95f9-393">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

> [!NOTE] 
> <span data-ttu-id="f95f9-394">Você pode configurar o Human Resources para exigir que Posições especifique um Departamento.</span><span class="sxs-lookup"><span data-stu-id="f95f9-394">You can configure Human Resources to require that Positions specify a Department.</span></span> <span data-ttu-id="f95f9-395">Para isso, acesse **Posições Compartilhadas de Recursos Humanos > Posições > Exigir departamentos nas posições**.</span><span class="sxs-lookup"><span data-stu-id="f95f9-395">To do this, go to **Human Resources Shared Positions > Positions > Require departments on positions**.</span></span> <span data-ttu-id="f95f9-396">Recomendamos que esta configuração seja imposta para a integração.</span><span class="sxs-lookup"><span data-stu-id="f95f9-396">We recommend that this setting be enforced for the integration.</span></span>

### <a name="job-types"></a><span data-ttu-id="f95f9-397">Tipos de trabalho</span><span class="sxs-lookup"><span data-stu-id="f95f9-397">Job types</span></span>

<span data-ttu-id="f95f9-398">Os tipos de trabalho são usados para agrupar trabalhos semelhantes em categorias.</span><span class="sxs-lookup"><span data-stu-id="f95f9-398">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="f95f9-399">Os tipos de trabalho são necessários para processar a folha de pagamento nos Estados Unidos e no Canadá.</span><span class="sxs-lookup"><span data-stu-id="f95f9-399">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="f95f9-400">Os exemplos de tipos de trabalho incluem horário integral e meio período ou salário e pagamento por hora.</span><span class="sxs-lookup"><span data-stu-id="f95f9-400">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="f95f9-401">Os tipos de trabalho são mapeados para o Dayforce como tipos de pagamento que indicam se um funcionário é pago por hora ou assalariado.</span><span class="sxs-lookup"><span data-stu-id="f95f9-401">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="f95f9-402">Os seguintes tipos de trabalho e descrições são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="f95f9-402">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="f95f9-403">Tipo de trabalho</span><span class="sxs-lookup"><span data-stu-id="f95f9-403">Job type</span></span>   | <span data-ttu-id="f95f9-404">descrição</span><span class="sxs-lookup"><span data-stu-id="f95f9-404">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="f95f9-405">Por hora</span><span class="sxs-lookup"><span data-stu-id="f95f9-405">Hourly</span></span>     | <span data-ttu-id="f95f9-406">Por hora</span><span class="sxs-lookup"><span data-stu-id="f95f9-406">Hourly</span></span>      |
| <span data-ttu-id="f95f9-407">Assalariado</span><span class="sxs-lookup"><span data-stu-id="f95f9-407">Salaried</span></span>   | <span data-ttu-id="f95f9-408">Assalariado</span><span class="sxs-lookup"><span data-stu-id="f95f9-408">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="f95f9-409">Tipos de posição</span><span class="sxs-lookup"><span data-stu-id="f95f9-409">Position types</span></span> 

<span data-ttu-id="f95f9-410">Você usa os tipos de posição para descrever se a posição é de tempo integral, meio período ou de outra natureza.</span><span class="sxs-lookup"><span data-stu-id="f95f9-410">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="f95f9-411">Os tipos de posição são mapeados para o Dayforce como classes de pagamento que indicam se um funcionário é de tempo integral ou meio período.</span><span class="sxs-lookup"><span data-stu-id="f95f9-411">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="f95f9-412">Os seguintes tipos de posição e descrições são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="f95f9-412">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="f95f9-413">Tipo de posição</span><span class="sxs-lookup"><span data-stu-id="f95f9-413">Position type</span></span>   | <span data-ttu-id="f95f9-414">descrição</span><span class="sxs-lookup"><span data-stu-id="f95f9-414">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="f95f9-415">Horário integral</span><span class="sxs-lookup"><span data-stu-id="f95f9-415">Full-time</span></span>       | <span data-ttu-id="f95f9-416">Funcionário de tempo integral</span><span class="sxs-lookup"><span data-stu-id="f95f9-416">Full time employee</span></span> |
| <span data-ttu-id="f95f9-417">Meio período</span><span class="sxs-lookup"><span data-stu-id="f95f9-417">Part-time</span></span>       | <span data-ttu-id="f95f9-418">Funcionário de meio período</span><span class="sxs-lookup"><span data-stu-id="f95f9-418">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="f95f9-419">Códigos de motivos</span><span class="sxs-lookup"><span data-stu-id="f95f9-419">Reason codes</span></span>

<span data-ttu-id="f95f9-420">Códigos de motivo fornecem informações sobre o status de um funcionário.</span><span class="sxs-lookup"><span data-stu-id="f95f9-420">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="f95f9-421">Os códigos de motivo são mapeados para o Dayforce como motivos de status que indicam o motivo das alterações na posição de um funcionário ou no status de um emprego.</span><span class="sxs-lookup"><span data-stu-id="f95f9-421">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="f95f9-422">Os seguintes códigos de motivo e descrições são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="f95f9-422">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="f95f9-423">Código de motivo</span><span class="sxs-lookup"><span data-stu-id="f95f9-423">Reason code</span></span>    | <span data-ttu-id="f95f9-424">descrição</span><span class="sxs-lookup"><span data-stu-id="f95f9-424">Description</span></span>      | <span data-ttu-id="f95f9-425">Cenários aplicáveis</span><span class="sxs-lookup"><span data-stu-id="f95f9-425">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="f95f9-426">DEMISSÃO</span><span class="sxs-lookup"><span data-stu-id="f95f9-426">RESIGNATION</span></span>    | <span data-ttu-id="f95f9-427">Demissão</span><span class="sxs-lookup"><span data-stu-id="f95f9-427">Resignation</span></span>      | <span data-ttu-id="f95f9-428">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="f95f9-428">Terminate worker</span></span>     |
| <span data-ttu-id="f95f9-429">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="f95f9-429">TERMINATION</span></span>    | <span data-ttu-id="f95f9-430">Finalização</span><span class="sxs-lookup"><span data-stu-id="f95f9-430">Termination</span></span>      | <span data-ttu-id="f95f9-431">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="f95f9-431">Terminate worker</span></span>     |
| <span data-ttu-id="f95f9-432">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="f95f9-432">RETIREMENT</span></span>     | <span data-ttu-id="f95f9-433">Aposentadoria</span><span class="sxs-lookup"><span data-stu-id="f95f9-433">Retirement</span></span>       | <span data-ttu-id="f95f9-434">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="f95f9-434">Terminate worker</span></span>     |
| <span data-ttu-id="f95f9-435">OTHER</span><span class="sxs-lookup"><span data-stu-id="f95f9-435">OTHER</span></span>          | <span data-ttu-id="f95f9-436">Outros motivos</span><span class="sxs-lookup"><span data-stu-id="f95f9-436">Other Reasons</span></span>    | <span data-ttu-id="f95f9-437">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="f95f9-437">Terminate worker</span></span>     |
| <span data-ttu-id="f95f9-438">DEATH</span><span class="sxs-lookup"><span data-stu-id="f95f9-438">DEATH</span></span>          | <span data-ttu-id="f95f9-439">Morte</span><span class="sxs-lookup"><span data-stu-id="f95f9-439">Death</span></span>            | <span data-ttu-id="f95f9-440">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="f95f9-440">Terminate worker</span></span>     |
| <span data-ttu-id="f95f9-441">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="f95f9-441">LEAVEOFABSENCE</span></span> | <span data-ttu-id="f95f9-442">Licença</span><span class="sxs-lookup"><span data-stu-id="f95f9-442">Leave of Absence</span></span> | <span data-ttu-id="f95f9-443">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="f95f9-443">Terminate worker</span></span>     |
| <span data-ttu-id="f95f9-444">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="f95f9-444">CONTRACTEND</span></span>    | <span data-ttu-id="f95f9-445">Fim do contrato</span><span class="sxs-lookup"><span data-stu-id="f95f9-445">End of Contract</span></span>  | <span data-ttu-id="f95f9-446">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="f95f9-446">Terminate worker</span></span>     |
| <span data-ttu-id="f95f9-447">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="f95f9-447">SALARYCHANGE</span></span>   | <span data-ttu-id="f95f9-448">Alteração de salário</span><span class="sxs-lookup"><span data-stu-id="f95f9-448">Change of Salary</span></span> | <span data-ttu-id="f95f9-449">Remuneração</span><span class="sxs-lookup"><span data-stu-id="f95f9-449">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="f95f9-450">Estado civil</span><span class="sxs-lookup"><span data-stu-id="f95f9-450">Marital status</span></span>

<span data-ttu-id="f95f9-451">Os valores do estado civil são mapeados para o Dayforce e convertidos, conforme apropriado, nos valores aceitos após a integração.</span><span class="sxs-lookup"><span data-stu-id="f95f9-451">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="f95f9-452">A tabela a seguir mostra como os valores do estado civil são mapeados para o Dayforce.</span><span class="sxs-lookup"><span data-stu-id="f95f9-452">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="f95f9-453">Recursos Humanos</span><span class="sxs-lookup"><span data-stu-id="f95f9-453">Human Resources</span></span>                 | <span data-ttu-id="f95f9-454">Dayforce</span><span class="sxs-lookup"><span data-stu-id="f95f9-454">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="f95f9-455">Casado(a)</span><span class="sxs-lookup"><span data-stu-id="f95f9-455">Married</span></span>                | <span data-ttu-id="f95f9-456">Casado(a)</span><span class="sxs-lookup"><span data-stu-id="f95f9-456">Married</span></span>              |
| <span data-ttu-id="f95f9-457">Único</span><span class="sxs-lookup"><span data-stu-id="f95f9-457">Single</span></span>                 | <span data-ttu-id="f95f9-458">Único</span><span class="sxs-lookup"><span data-stu-id="f95f9-458">Single</span></span>               |
| <span data-ttu-id="f95f9-459">Viúvo(a)</span><span class="sxs-lookup"><span data-stu-id="f95f9-459">Widowed</span></span>                | <span data-ttu-id="f95f9-460">Viúvo(a)</span><span class="sxs-lookup"><span data-stu-id="f95f9-460">Widowed</span></span>              |
| <span data-ttu-id="f95f9-461">Divorciado(a)</span><span class="sxs-lookup"><span data-stu-id="f95f9-461">Divorced</span></span>               | <span data-ttu-id="f95f9-462">Divorciado(a)</span><span class="sxs-lookup"><span data-stu-id="f95f9-462">Divorced</span></span>             |
| <span data-ttu-id="f95f9-463">Parceria Registrada</span><span class="sxs-lookup"><span data-stu-id="f95f9-463">Registered Partnership</span></span> | <span data-ttu-id="f95f9-464">Parceiro doméstico</span><span class="sxs-lookup"><span data-stu-id="f95f9-464">Domestic Partnership</span></span> |
| <span data-ttu-id="f95f9-465">Nenhum(a)</span><span class="sxs-lookup"><span data-stu-id="f95f9-465">None</span></span>                   | <span data-ttu-id="f95f9-466">Nenhum(a)</span><span class="sxs-lookup"><span data-stu-id="f95f9-466">None</span></span>                 |
| <span data-ttu-id="f95f9-467">Coabitando</span><span class="sxs-lookup"><span data-stu-id="f95f9-467">Cohabiting</span></span>             | <span data-ttu-id="f95f9-468">Coabitando</span><span class="sxs-lookup"><span data-stu-id="f95f9-468">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="f95f9-469">Sexo</span><span class="sxs-lookup"><span data-stu-id="f95f9-469">Gender</span></span>

<span data-ttu-id="f95f9-470">As designações de gênero são mapeadas para o Dayforce e convertidas, conforme apropriado, nos valores aceitos após a integração.</span><span class="sxs-lookup"><span data-stu-id="f95f9-470">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="f95f9-471">A tabela a seguir mostra como as designações de gênero são mapeadas para o Dayforce.</span><span class="sxs-lookup"><span data-stu-id="f95f9-471">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="f95f9-472">Recursos Humanos</span><span class="sxs-lookup"><span data-stu-id="f95f9-472">Human Resources</span></span>       | <span data-ttu-id="f95f9-473">Dayforce</span><span class="sxs-lookup"><span data-stu-id="f95f9-473">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="f95f9-474">Masculino</span><span class="sxs-lookup"><span data-stu-id="f95f9-474">Male</span></span>         | <span data-ttu-id="f95f9-475">Masculino</span><span class="sxs-lookup"><span data-stu-id="f95f9-475">Male</span></span>            |
| <span data-ttu-id="f95f9-476">Feminino</span><span class="sxs-lookup"><span data-stu-id="f95f9-476">Female</span></span>       | <span data-ttu-id="f95f9-477">Feminino</span><span class="sxs-lookup"><span data-stu-id="f95f9-477">Female</span></span>          |
| <span data-ttu-id="f95f9-478">Não específico</span><span class="sxs-lookup"><span data-stu-id="f95f9-478">Non-specific</span></span> | <span data-ttu-id="f95f9-479">*Sem suporte*</span><span class="sxs-lookup"><span data-stu-id="f95f9-479">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="f95f9-480">Códigos de ganhos</span><span class="sxs-lookup"><span data-stu-id="f95f9-480">Earning codes</span></span>

<span data-ttu-id="f95f9-481">Os códigos de ganhos identificam de forma exclusiva cada tipo de ganho que os trabalhadores recebem.</span><span class="sxs-lookup"><span data-stu-id="f95f9-481">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="f95f9-482">Os códigos abordam vários parâmetros relacionados a ganhos, como regras contábeis, leis tributárias, requisitos de relatório e capacidade de montante bruto.</span><span class="sxs-lookup"><span data-stu-id="f95f9-482">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="f95f9-483">Se uma frequência sem suporte for usada, a frequência **Cada pagamento** é usada por padrão para o cálculo.</span><span class="sxs-lookup"><span data-stu-id="f95f9-483">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="f95f9-484">Frequências com suporte</span><span class="sxs-lookup"><span data-stu-id="f95f9-484">Supported frequencies</span></span>

- <span data-ttu-id="f95f9-485">Todas</span><span class="sxs-lookup"><span data-stu-id="f95f9-485">All</span></span>
- <span data-ttu-id="f95f9-486">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="f95f9-486">EVERYPAY</span></span>
- <span data-ttu-id="f95f9-487">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="f95f9-487">EACHPAYPERIOD</span></span>
- <span data-ttu-id="f95f9-488">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="f95f9-488">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="f95f9-489">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="f95f9-489">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="f95f9-490">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="f95f9-490">1OFMTH</span></span>
- <span data-ttu-id="f95f9-491">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="f95f9-491">LASTOFMTH</span></span>
- <span data-ttu-id="f95f9-492">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="f95f9-492">2OFMTH</span></span>
- <span data-ttu-id="f95f9-493">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="f95f9-493">3OFMTH</span></span>
- <span data-ttu-id="f95f9-494">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="f95f9-494">4OFMTH</span></span>
- <span data-ttu-id="f95f9-495">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="f95f9-495">5OFMTH</span></span>
- <span data-ttu-id="f95f9-496">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="f95f9-496">1N2OFMTH</span></span>
- <span data-ttu-id="f95f9-497">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="f95f9-497">3N4OFMTH</span></span>
- <span data-ttu-id="f95f9-498">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="f95f9-498">1N3OFMTH</span></span>
- <span data-ttu-id="f95f9-499">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="f95f9-499">1N4OFMTH</span></span>
- <span data-ttu-id="f95f9-500">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="f95f9-500">2N3OFMTH</span></span>
- <span data-ttu-id="f95f9-501">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="f95f9-501">2N4OFMTH</span></span>
- <span data-ttu-id="f95f9-502">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="f95f9-502">1N2N3OFMTH</span></span>
- <span data-ttu-id="f95f9-503">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="f95f9-503">1N2N4OFMTH</span></span>
- <span data-ttu-id="f95f9-504">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="f95f9-504">1N3N4OFMTH</span></span>
- <span data-ttu-id="f95f9-505">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="f95f9-505">2N3N4OFMTH</span></span>
- <span data-ttu-id="f95f9-506">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="f95f9-506">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="f95f9-507">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="f95f9-507">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="f95f9-508">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="f95f9-508">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="f95f9-509">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="f95f9-509">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="f95f9-510">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="f95f9-510">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="f95f9-511">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="f95f9-511">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="f95f9-512">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="f95f9-512">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="f95f9-513">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="f95f9-513">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="f95f9-514">Endereços</span><span class="sxs-lookup"><span data-stu-id="f95f9-514">Addresses</span></span>

<span data-ttu-id="f95f9-515">A identificação de códigos específicos de país ou região, estado e município (municipalidade) exige formatos específicos que o Dayforce e os provedores no país/na região possam reconhecer.</span><span class="sxs-lookup"><span data-stu-id="f95f9-515">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="f95f9-516">Embora o formato das cidades seja flexível, todas as cidades devem estar associadas a um estado.</span><span class="sxs-lookup"><span data-stu-id="f95f9-516">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="f95f9-517">Recursos Humanos</span><span class="sxs-lookup"><span data-stu-id="f95f9-517">Human Resources</span></span>          | <span data-ttu-id="f95f9-518">Dayforce</span><span class="sxs-lookup"><span data-stu-id="f95f9-518">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="f95f9-519">País/Região</span><span class="sxs-lookup"><span data-stu-id="f95f9-519">Country/Region</span></span>  | <span data-ttu-id="f95f9-520">Código do País</span><span class="sxs-lookup"><span data-stu-id="f95f9-520">Country Code</span></span>          |
| <span data-ttu-id="f95f9-521">CEP</span><span class="sxs-lookup"><span data-stu-id="f95f9-521">Zip/Postal Code</span></span> | <span data-ttu-id="f95f9-522">CEP</span><span class="sxs-lookup"><span data-stu-id="f95f9-522">Postal Code</span></span>           |
| <span data-ttu-id="f95f9-523">Estadual</span><span class="sxs-lookup"><span data-stu-id="f95f9-523">State</span></span>           | <span data-ttu-id="f95f9-524">Código de estado</span><span class="sxs-lookup"><span data-stu-id="f95f9-524">State Code</span></span>            |
| <span data-ttu-id="f95f9-525">Cidade</span><span class="sxs-lookup"><span data-stu-id="f95f9-525">City</span></span>            | <span data-ttu-id="f95f9-526">Cidade</span><span class="sxs-lookup"><span data-stu-id="f95f9-526">City</span></span>                  |
| <span data-ttu-id="f95f9-527">Região</span><span class="sxs-lookup"><span data-stu-id="f95f9-527">County</span></span>          | <span data-ttu-id="f95f9-528">Município (municipalidade)</span><span class="sxs-lookup"><span data-stu-id="f95f9-528">County (Municipality)</span></span> |
| <span data-ttu-id="f95f9-529">Rua</span><span class="sxs-lookup"><span data-stu-id="f95f9-529">Street</span></span>          | <span data-ttu-id="f95f9-530">Linha de endereço 1</span><span class="sxs-lookup"><span data-stu-id="f95f9-530">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="f95f9-531">Regiões fiscais</span><span class="sxs-lookup"><span data-stu-id="f95f9-531">Tax regions</span></span>

<span data-ttu-id="f95f9-532">Regiões fiscais são usadas para determinar os impostos apropriados a serem aplicados durante a geração da folha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="f95f9-532">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="f95f9-533">As regiões fiscais são mapeadas para o Dayforce como endereços de localização.</span><span class="sxs-lookup"><span data-stu-id="f95f9-533">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="f95f9-534">A região fiscal padrão deve estar associada à posição ativa do trabalhador.</span><span class="sxs-lookup"><span data-stu-id="f95f9-534">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="f95f9-535">Região fiscal (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="f95f9-535">Tax region (required)</span></span>
- <span data-ttu-id="f95f9-536">País/região (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-536">Country/Region (required)</span></span>
- <span data-ttu-id="f95f9-537">Estado (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f95f9-537">State (required)</span></span>
- <span data-ttu-id="f95f9-538">Região</span><span class="sxs-lookup"><span data-stu-id="f95f9-538">County</span></span> 
- <span data-ttu-id="f95f9-539">Cidade (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="f95f9-539">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="f95f9-540">Configurar seus dados para gerar folha de pagamento no México</span><span class="sxs-lookup"><span data-stu-id="f95f9-540">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="f95f9-541">Se você está gerando pagamento para funcionários no México, os seguintes elementos devem ser configurados:</span><span class="sxs-lookup"><span data-stu-id="f95f9-541">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="f95f9-542">Departamentos são necessários em posições.</span><span class="sxs-lookup"><span data-stu-id="f95f9-542">Departments are required on positions.</span></span>
- <span data-ttu-id="f95f9-543">Os centros de custo devem ser definidos como dimensões financeiras e ser o primeiro elemento na sequência de dimensão financeira padrão.</span><span class="sxs-lookup"><span data-stu-id="f95f9-543">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="f95f9-544">Tipos de trabalho</span><span class="sxs-lookup"><span data-stu-id="f95f9-544">Job types</span></span>

<span data-ttu-id="f95f9-545">Os tipos de trabalho são usados para agrupar trabalhos semelhantes em categorias.</span><span class="sxs-lookup"><span data-stu-id="f95f9-545">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="f95f9-546">Tipos de trabalho são necessários para processar a folha de pagamento no México.</span><span class="sxs-lookup"><span data-stu-id="f95f9-546">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="f95f9-547">Os exemplos de tipos de trabalho incluem horário integral e meio período ou salário e pagamento por hora.</span><span class="sxs-lookup"><span data-stu-id="f95f9-547">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="f95f9-548">Os tipos de trabalho são mapeados para o Dayforce como tipos de pagamento que indicam se um funcionário é pago por hora ou assalariado.</span><span class="sxs-lookup"><span data-stu-id="f95f9-548">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="f95f9-549">Os seguintes tipos de trabalho e descrições são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="f95f9-549">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="f95f9-550">Tipo de trabalho</span><span class="sxs-lookup"><span data-stu-id="f95f9-550">Job type</span></span>   | <span data-ttu-id="f95f9-551">descrição</span><span class="sxs-lookup"><span data-stu-id="f95f9-551">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="f95f9-552">Por hora</span><span class="sxs-lookup"><span data-stu-id="f95f9-552">Hourly</span></span>     | <span data-ttu-id="f95f9-553">MX por hora</span><span class="sxs-lookup"><span data-stu-id="f95f9-553">MX Hourly</span></span>   |
| <span data-ttu-id="f95f9-554">Assalariado</span><span class="sxs-lookup"><span data-stu-id="f95f9-554">Salaried</span></span>   | <span data-ttu-id="f95f9-555">MX assalariado</span><span class="sxs-lookup"><span data-stu-id="f95f9-555">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="f95f9-556">Tipos de posição</span><span class="sxs-lookup"><span data-stu-id="f95f9-556">Position types</span></span> 

<span data-ttu-id="f95f9-557">Você usa os tipos de posição para descrever se a posição é de tempo integral, meio período ou de outra natureza.</span><span class="sxs-lookup"><span data-stu-id="f95f9-557">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="f95f9-558">Os tipos de posição são mapeados para o Dayforce como classes de pagamento que indicam se um funcionário é de tempo integral ou meio período.</span><span class="sxs-lookup"><span data-stu-id="f95f9-558">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="f95f9-559">Os seguintes tipos de posição e descrições são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="f95f9-559">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="f95f9-560">Tipo de posição</span><span class="sxs-lookup"><span data-stu-id="f95f9-560">Position type</span></span>   | <span data-ttu-id="f95f9-561">descrição</span><span class="sxs-lookup"><span data-stu-id="f95f9-561">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="f95f9-562">Horário integral</span><span class="sxs-lookup"><span data-stu-id="f95f9-562">Full-time</span></span>       | <span data-ttu-id="f95f9-563">Funcionário de tempo integral</span><span class="sxs-lookup"><span data-stu-id="f95f9-563">Full time employee</span></span> |
| <span data-ttu-id="f95f9-564">Meio período</span><span class="sxs-lookup"><span data-stu-id="f95f9-564">Part-time</span></span>       | <span data-ttu-id="f95f9-565">Funcionário de meio período</span><span class="sxs-lookup"><span data-stu-id="f95f9-565">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="f95f9-566">Códigos de motivos</span><span class="sxs-lookup"><span data-stu-id="f95f9-566">Reason codes</span></span>

<span data-ttu-id="f95f9-567">Códigos de motivo fornecem informações sobre o status de um funcionário.</span><span class="sxs-lookup"><span data-stu-id="f95f9-567">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="f95f9-568">Os códigos de motivo são mapeados para o Dayforce como motivos de status que indicam o motivo das alterações na posição de um funcionário ou no status de um emprego.</span><span class="sxs-lookup"><span data-stu-id="f95f9-568">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="f95f9-569">Os seguintes códigos de motivo e descrições são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="f95f9-569">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="f95f9-570">Código de motivo</span><span class="sxs-lookup"><span data-stu-id="f95f9-570">Reason code</span></span>            | <span data-ttu-id="f95f9-571">descrição</span><span class="sxs-lookup"><span data-stu-id="f95f9-571">Description</span></span>                    | <span data-ttu-id="f95f9-572">Cenários aplicáveis</span><span class="sxs-lookup"><span data-stu-id="f95f9-572">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="f95f9-573">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="f95f9-573">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="f95f9-574">Partida antes da primeira folha de pagamento</span><span class="sxs-lookup"><span data-stu-id="f95f9-574">Departure before first payroll</span></span> | <span data-ttu-id="f95f9-575">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="f95f9-575">Terminate worker</span></span>     |
| <span data-ttu-id="f95f9-576">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="f95f9-576">RESIGNATION</span></span>            | <span data-ttu-id="f95f9-577">Demissão</span><span class="sxs-lookup"><span data-stu-id="f95f9-577">Resignation</span></span>                    | <span data-ttu-id="f95f9-578">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="f95f9-578">Terminate worker</span></span>     |
| <span data-ttu-id="f95f9-579">PENSION</span><span class="sxs-lookup"><span data-stu-id="f95f9-579">PENSION</span></span>                | <span data-ttu-id="f95f9-580">Aposentadoria</span><span class="sxs-lookup"><span data-stu-id="f95f9-580">Pension</span></span>                        | <span data-ttu-id="f95f9-581">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="f95f9-581">Terminate worker</span></span>     |
| <span data-ttu-id="f95f9-582">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="f95f9-582">TERMINATION</span></span>            | <span data-ttu-id="f95f9-583">Finalização</span><span class="sxs-lookup"><span data-stu-id="f95f9-583">Termination</span></span>                    | <span data-ttu-id="f95f9-584">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="f95f9-584">Terminate worker</span></span>     |
| <span data-ttu-id="f95f9-585">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="f95f9-585">RETIREMENT</span></span>             | <span data-ttu-id="f95f9-586">Aposentadoria</span><span class="sxs-lookup"><span data-stu-id="f95f9-586">Retirement</span></span>                     | <span data-ttu-id="f95f9-587">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="f95f9-587">Terminate worker</span></span>     |
| <span data-ttu-id="f95f9-588">ABSENTEE</span><span class="sxs-lookup"><span data-stu-id="f95f9-588">ABSENTEE</span></span>               | <span data-ttu-id="f95f9-589">Absentista</span><span class="sxs-lookup"><span data-stu-id="f95f9-589">Absentee</span></span>                       | <span data-ttu-id="f95f9-590">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="f95f9-590">Terminate worker</span></span>     |
| <span data-ttu-id="f95f9-591">OTHER</span><span class="sxs-lookup"><span data-stu-id="f95f9-591">OTHER</span></span>                  | <span data-ttu-id="f95f9-592">Outros motivos</span><span class="sxs-lookup"><span data-stu-id="f95f9-592">Other Reasons</span></span>                  | <span data-ttu-id="f95f9-593">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="f95f9-593">Terminate worker</span></span>     |
| <span data-ttu-id="f95f9-594">CLOSURE</span><span class="sxs-lookup"><span data-stu-id="f95f9-594">CLOSURE</span></span>                | <span data-ttu-id="f95f9-595">Fechamento da empresa</span><span class="sxs-lookup"><span data-stu-id="f95f9-595">Business Closure</span></span>               | <span data-ttu-id="f95f9-596">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="f95f9-596">Terminate worker</span></span>     |
| <span data-ttu-id="f95f9-597">DEATH</span><span class="sxs-lookup"><span data-stu-id="f95f9-597">DEATH</span></span>                  | <span data-ttu-id="f95f9-598">Morte</span><span class="sxs-lookup"><span data-stu-id="f95f9-598">Death</span></span>                          | <span data-ttu-id="f95f9-599">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="f95f9-599">Terminate worker</span></span>     |
| <span data-ttu-id="f95f9-600">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="f95f9-600">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="f95f9-601">Licença</span><span class="sxs-lookup"><span data-stu-id="f95f9-601">Leave of Absence</span></span>               | <span data-ttu-id="f95f9-602">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="f95f9-602">Terminate worker</span></span>     |
| <span data-ttu-id="f95f9-603">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="f95f9-603">CONTRACTEND</span></span>            | <span data-ttu-id="f95f9-604">Fim do contrato</span><span class="sxs-lookup"><span data-stu-id="f95f9-604">End of Contract</span></span>                | <span data-ttu-id="f95f9-605">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="f95f9-605">Terminate worker</span></span>     |
| <span data-ttu-id="f95f9-606">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="f95f9-606">SALARYCHANGE</span></span>           | <span data-ttu-id="f95f9-607">Alteração de salário</span><span class="sxs-lookup"><span data-stu-id="f95f9-607">Change of Salary</span></span>               | <span data-ttu-id="f95f9-608">Remuneração</span><span class="sxs-lookup"><span data-stu-id="f95f9-608">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="f95f9-609">Contrato de trabalho</span><span class="sxs-lookup"><span data-stu-id="f95f9-609">Terms of employment</span></span>

<span data-ttu-id="f95f9-610">Termos de emprego são usados para criar categorias de termos de emprego.</span><span class="sxs-lookup"><span data-stu-id="f95f9-610">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="f95f9-611">Os termos são mapeados para o Dayforce como valores de indicador de emprego.</span><span class="sxs-lookup"><span data-stu-id="f95f9-611">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="f95f9-612">Os termos de emprego e as descrições a seguir são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="f95f9-612">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="f95f9-613">Contrato de trabalho</span><span class="sxs-lookup"><span data-stu-id="f95f9-613">Terms of employment</span></span>   | <span data-ttu-id="f95f9-614">descrição</span><span class="sxs-lookup"><span data-stu-id="f95f9-614">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="f95f9-615">Normal</span><span class="sxs-lookup"><span data-stu-id="f95f9-615">Regular</span></span>               | <span data-ttu-id="f95f9-616">Normal</span><span class="sxs-lookup"><span data-stu-id="f95f9-616">Regular</span></span>     |
| <span data-ttu-id="f95f9-617">Direto</span><span class="sxs-lookup"><span data-stu-id="f95f9-617">Direct</span></span>                | <span data-ttu-id="f95f9-618">Direto</span><span class="sxs-lookup"><span data-stu-id="f95f9-618">Direct</span></span>      |
| <span data-ttu-id="f95f9-619">Estágio</span><span class="sxs-lookup"><span data-stu-id="f95f9-619">Internship</span></span>            | <span data-ttu-id="f95f9-620">Estágio</span><span class="sxs-lookup"><span data-stu-id="f95f9-620">Internship</span></span>  |
| <span data-ttu-id="f95f9-621">Permanente</span><span class="sxs-lookup"><span data-stu-id="f95f9-621">Permanent</span></span>             | <span data-ttu-id="f95f9-622">Permanente</span><span class="sxs-lookup"><span data-stu-id="f95f9-622">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="f95f9-623">Estado civil</span><span class="sxs-lookup"><span data-stu-id="f95f9-623">Marital status</span></span>

<span data-ttu-id="f95f9-624">Os valores do estado civil são mapeados para o Dayforce e convertidos, conforme apropriado, nos valores aceitos após a integração.</span><span class="sxs-lookup"><span data-stu-id="f95f9-624">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="f95f9-625">A tabela a seguir mostra como os valores do estado civil são mapeados para o Dayforce.</span><span class="sxs-lookup"><span data-stu-id="f95f9-625">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="f95f9-626">Recursos Humanos</span><span class="sxs-lookup"><span data-stu-id="f95f9-626">Human Resources</span></span>                 | <span data-ttu-id="f95f9-627">Dayforce</span><span class="sxs-lookup"><span data-stu-id="f95f9-627">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="f95f9-628">Casado(a)</span><span class="sxs-lookup"><span data-stu-id="f95f9-628">Married</span></span>                | <span data-ttu-id="f95f9-629">Casado(a)</span><span class="sxs-lookup"><span data-stu-id="f95f9-629">Married</span></span>                   |
| <span data-ttu-id="f95f9-630">Único</span><span class="sxs-lookup"><span data-stu-id="f95f9-630">Single</span></span>                 | <span data-ttu-id="f95f9-631">Único</span><span class="sxs-lookup"><span data-stu-id="f95f9-631">Single</span></span>                    |
| <span data-ttu-id="f95f9-632">Viúvo(a)</span><span class="sxs-lookup"><span data-stu-id="f95f9-632">Widowed</span></span>                | <span data-ttu-id="f95f9-633">Viúvo(a)</span><span class="sxs-lookup"><span data-stu-id="f95f9-633">Widowed</span></span>                   |
| <span data-ttu-id="f95f9-634">Divorciado(a)</span><span class="sxs-lookup"><span data-stu-id="f95f9-634">Divorced</span></span>               | <span data-ttu-id="f95f9-635">Divorciado(a)</span><span class="sxs-lookup"><span data-stu-id="f95f9-635">Divorced</span></span>                  |
| <span data-ttu-id="f95f9-636">Parceria Registrada</span><span class="sxs-lookup"><span data-stu-id="f95f9-636">Registered Partnership</span></span> | <span data-ttu-id="f95f9-637">Parceiro doméstico</span><span class="sxs-lookup"><span data-stu-id="f95f9-637">Domestic Partnership</span></span>      |
| <span data-ttu-id="f95f9-638">Nenhum(a)</span><span class="sxs-lookup"><span data-stu-id="f95f9-638">None</span></span>                   | <span data-ttu-id="f95f9-639">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="f95f9-639">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="f95f9-640">Coabitando</span><span class="sxs-lookup"><span data-stu-id="f95f9-640">Cohabiting</span></span>             | <span data-ttu-id="f95f9-641">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="f95f9-641">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="f95f9-642">Sexo</span><span class="sxs-lookup"><span data-stu-id="f95f9-642">Gender</span></span>

<span data-ttu-id="f95f9-643">As designações de gênero são mapeadas para o Dayforce e convertidas, conforme apropriado, nos valores aceitos após a integração.</span><span class="sxs-lookup"><span data-stu-id="f95f9-643">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="f95f9-644">A tabela a seguir mostra como as designações de gênero são mapeadas para o Dayforce.</span><span class="sxs-lookup"><span data-stu-id="f95f9-644">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="f95f9-645">Recursos Humanos</span><span class="sxs-lookup"><span data-stu-id="f95f9-645">Human Resources</span></span>       | <span data-ttu-id="f95f9-646">Dayforce</span><span class="sxs-lookup"><span data-stu-id="f95f9-646">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="f95f9-647">Masculino</span><span class="sxs-lookup"><span data-stu-id="f95f9-647">Male</span></span>         | <span data-ttu-id="f95f9-648">Masculino</span><span class="sxs-lookup"><span data-stu-id="f95f9-648">Male</span></span>                      |
| <span data-ttu-id="f95f9-649">Feminino</span><span class="sxs-lookup"><span data-stu-id="f95f9-649">Female</span></span>       | <span data-ttu-id="f95f9-650">Feminino</span><span class="sxs-lookup"><span data-stu-id="f95f9-650">Female</span></span>                    |
| <span data-ttu-id="f95f9-651">Não específico</span><span class="sxs-lookup"><span data-stu-id="f95f9-651">Non-specific</span></span> | <span data-ttu-id="f95f9-652">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="f95f9-652">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="f95f9-653">Forma de pagamento</span><span class="sxs-lookup"><span data-stu-id="f95f9-653">Payment method</span></span>

<span data-ttu-id="f95f9-654">Os métodos de pagamento dão ao funcionário e à empresa uma maneira de descrever como os funcionários serão pagos.</span><span class="sxs-lookup"><span data-stu-id="f95f9-654">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="f95f9-655">Os métodos de pagamento são mapeados para o Dayforce e convertidos, conforme apropriado, nos valores aceitos após a integração.</span><span class="sxs-lookup"><span data-stu-id="f95f9-655">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="f95f9-656">A tabela a seguir mostra como os métodos de pagamento são mapeados para o Dayforce.</span><span class="sxs-lookup"><span data-stu-id="f95f9-656">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="f95f9-657">Recursos Humanos</span><span class="sxs-lookup"><span data-stu-id="f95f9-657">Human Resources</span></span>             | <span data-ttu-id="f95f9-658">Dayforce</span><span class="sxs-lookup"><span data-stu-id="f95f9-658">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="f95f9-659">Pagamento à vista</span><span class="sxs-lookup"><span data-stu-id="f95f9-659">Cash</span></span>               | <span data-ttu-id="f95f9-660">Pagamento à vista</span><span class="sxs-lookup"><span data-stu-id="f95f9-660">Cash</span></span>                      |
| <span data-ttu-id="f95f9-661">Pagamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="f95f9-661">Electronic Payment</span></span> | <span data-ttu-id="f95f9-662">Transferir</span><span class="sxs-lookup"><span data-stu-id="f95f9-662">Transfer</span></span>                  |
| <span data-ttu-id="f95f9-663">Marcar</span><span class="sxs-lookup"><span data-stu-id="f95f9-663">Check</span></span>              | <span data-ttu-id="f95f9-664">Cheque</span><span class="sxs-lookup"><span data-stu-id="f95f9-664">Cheque</span></span>                    |
| <span data-ttu-id="f95f9-665">Boleto bancário</span><span class="sxs-lookup"><span data-stu-id="f95f9-665">Bank Draft</span></span>         | <span data-ttu-id="f95f9-666">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="f95f9-666">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="f95f9-667">Outros</span><span class="sxs-lookup"><span data-stu-id="f95f9-667">Other</span></span>              | <span data-ttu-id="f95f9-668">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="f95f9-668">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="f95f9-669">Tipo de conta bancária</span><span class="sxs-lookup"><span data-stu-id="f95f9-669">Bank account type</span></span>

<span data-ttu-id="f95f9-670">Os tipos de conta bancária são usados para pagamentos eletrônicos aos funcionários.</span><span class="sxs-lookup"><span data-stu-id="f95f9-670">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="f95f9-671">Os tipos de conta bancária são mapeados para o Dayforce como informações da conta de transferência.</span><span class="sxs-lookup"><span data-stu-id="f95f9-671">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="f95f9-672">Os tipos de conta bancária são convertidos, conforme apropriado, nos valores aceitos após a integração.</span><span class="sxs-lookup"><span data-stu-id="f95f9-672">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="f95f9-673">Recursos Humanos</span><span class="sxs-lookup"><span data-stu-id="f95f9-673">Human Resources</span></span>            | <span data-ttu-id="f95f9-674">Dayforce</span><span class="sxs-lookup"><span data-stu-id="f95f9-674">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="f95f9-675">Conta corrente</span><span class="sxs-lookup"><span data-stu-id="f95f9-675">Checking Account</span></span>  | <span data-ttu-id="f95f9-676">CheckingAccount</span><span class="sxs-lookup"><span data-stu-id="f95f9-676">CheckingAccount</span></span>           |
| <span data-ttu-id="f95f9-677">Conta-salário</span><span class="sxs-lookup"><span data-stu-id="f95f9-677">Payroll Account</span></span>   | <span data-ttu-id="f95f9-678">PayrollAccount</span><span class="sxs-lookup"><span data-stu-id="f95f9-678">PayrollAccount</span></span>            |
| <span data-ttu-id="f95f9-679">Conta de poupança</span><span class="sxs-lookup"><span data-stu-id="f95f9-679">Savings Account</span></span>   | <span data-ttu-id="f95f9-680">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="f95f9-680">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="f95f9-681">Conta BankGirot</span><span class="sxs-lookup"><span data-stu-id="f95f9-681">BankGirot account</span></span> | <span data-ttu-id="f95f9-682">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="f95f9-682">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="f95f9-683">Conta PlusGirot</span><span class="sxs-lookup"><span data-stu-id="f95f9-683">PlusGirot account</span></span> | <span data-ttu-id="f95f9-684">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="f95f9-684">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="f95f9-685">Códigos de ganhos</span><span class="sxs-lookup"><span data-stu-id="f95f9-685">Earning codes</span></span>

<span data-ttu-id="f95f9-686">Os códigos de ganhos identificam de forma exclusiva cada tipo de ganho que os trabalhadores recebem.</span><span class="sxs-lookup"><span data-stu-id="f95f9-686">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="f95f9-687">Os códigos abordam vários parâmetros relacionados a ganhos, como regras contábeis, leis tributárias, requisitos de relatório e capacidade de montante bruto.</span><span class="sxs-lookup"><span data-stu-id="f95f9-687">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="f95f9-688">Se uma frequência sem suporte for usada, a frequência **Cada pagamento** é usada por padrão para o cálculo.</span><span class="sxs-lookup"><span data-stu-id="f95f9-688">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="f95f9-689">Frequências com suporte</span><span class="sxs-lookup"><span data-stu-id="f95f9-689">Supported frequencies</span></span>

- <span data-ttu-id="f95f9-690">Todas</span><span class="sxs-lookup"><span data-stu-id="f95f9-690">All</span></span>
- <span data-ttu-id="f95f9-691">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="f95f9-691">EVERYPAY</span></span>
- <span data-ttu-id="f95f9-692">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="f95f9-692">EACHPAYPERIOD</span></span>
- <span data-ttu-id="f95f9-693">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="f95f9-693">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="f95f9-694">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="f95f9-694">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="f95f9-695">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="f95f9-695">1OFMTH</span></span>
- <span data-ttu-id="f95f9-696">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="f95f9-696">LASTOFMTH</span></span>
- <span data-ttu-id="f95f9-697">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="f95f9-697">2OFMTH</span></span>
- <span data-ttu-id="f95f9-698">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="f95f9-698">3OFMTH</span></span>
- <span data-ttu-id="f95f9-699">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="f95f9-699">4OFMTH</span></span>
- <span data-ttu-id="f95f9-700">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="f95f9-700">5OFMTH</span></span>
- <span data-ttu-id="f95f9-701">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="f95f9-701">1N2OFMTH</span></span>
- <span data-ttu-id="f95f9-702">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="f95f9-702">3N4OFMTH</span></span>
- <span data-ttu-id="f95f9-703">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="f95f9-703">1N3OFMTH</span></span>
- <span data-ttu-id="f95f9-704">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="f95f9-704">1N4OFMTH</span></span>
- <span data-ttu-id="f95f9-705">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="f95f9-705">2N3OFMTH</span></span>
- <span data-ttu-id="f95f9-706">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="f95f9-706">2N4OFMTH</span></span>
- <span data-ttu-id="f95f9-707">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="f95f9-707">1N2N3OFMTH</span></span>
- <span data-ttu-id="f95f9-708">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="f95f9-708">1N2N4OFMTH</span></span>
- <span data-ttu-id="f95f9-709">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="f95f9-709">1N3N4OFMTH</span></span>
- <span data-ttu-id="f95f9-710">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="f95f9-710">2N3N4OFMTH</span></span>
- <span data-ttu-id="f95f9-711">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="f95f9-711">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="f95f9-712">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="f95f9-712">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="f95f9-713">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="f95f9-713">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="f95f9-714">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="f95f9-714">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="f95f9-715">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="f95f9-715">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="f95f9-716">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="f95f9-716">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="f95f9-717">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="f95f9-717">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="f95f9-718">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="f95f9-718">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="f95f9-719">Endereços</span><span class="sxs-lookup"><span data-stu-id="f95f9-719">Addresses</span></span>

<span data-ttu-id="f95f9-720">A identificação de códigos específicos de país ou região, estado e município (municipalidade) exige formatos específicos que o Dayforce e os provedores no país/na região possam reconhecer.</span><span class="sxs-lookup"><span data-stu-id="f95f9-720">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="f95f9-721">Embora o formato das cidades seja flexível, todas as cidades devem estar associadas a um estado.</span><span class="sxs-lookup"><span data-stu-id="f95f9-721">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="f95f9-722">Recursos Humanos</span><span class="sxs-lookup"><span data-stu-id="f95f9-722">Human Resources</span></span>              | <span data-ttu-id="f95f9-723">Dayforce</span><span class="sxs-lookup"><span data-stu-id="f95f9-723">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="f95f9-724">País/Região</span><span class="sxs-lookup"><span data-stu-id="f95f9-724">Country/Region</span></span>      | <span data-ttu-id="f95f9-725">Código do País</span><span class="sxs-lookup"><span data-stu-id="f95f9-725">Country Code</span></span>          |
| <span data-ttu-id="f95f9-726">CEP</span><span class="sxs-lookup"><span data-stu-id="f95f9-726">Zip/Postal Code</span></span>     | <span data-ttu-id="f95f9-727">CEP</span><span class="sxs-lookup"><span data-stu-id="f95f9-727">Postal Code</span></span>           |
| <span data-ttu-id="f95f9-728">Estadual</span><span class="sxs-lookup"><span data-stu-id="f95f9-728">State</span></span>               | <span data-ttu-id="f95f9-729">Código de estado</span><span class="sxs-lookup"><span data-stu-id="f95f9-729">State Code</span></span>            |
| <span data-ttu-id="f95f9-730">Cidade</span><span class="sxs-lookup"><span data-stu-id="f95f9-730">City</span></span>                | <span data-ttu-id="f95f9-731">Cidade</span><span class="sxs-lookup"><span data-stu-id="f95f9-731">City</span></span>                  |
| <span data-ttu-id="f95f9-732">Região</span><span class="sxs-lookup"><span data-stu-id="f95f9-732">County</span></span>              | <span data-ttu-id="f95f9-733">Município (municipalidade)</span><span class="sxs-lookup"><span data-stu-id="f95f9-733">County (Municipality)</span></span> |
| <span data-ttu-id="f95f9-734">Rua</span><span class="sxs-lookup"><span data-stu-id="f95f9-734">Street</span></span>              | <span data-ttu-id="f95f9-735">Linha de endereço 1</span><span class="sxs-lookup"><span data-stu-id="f95f9-735">Address Line 1</span></span>        |
| <span data-ttu-id="f95f9-736">Número</span><span class="sxs-lookup"><span data-stu-id="f95f9-736">Street Number</span></span>       | <span data-ttu-id="f95f9-737">Linha de endereço 2</span><span class="sxs-lookup"><span data-stu-id="f95f9-737">Address Line 2</span></span>        |
| <span data-ttu-id="f95f9-738">Complemento do edifício</span><span class="sxs-lookup"><span data-stu-id="f95f9-738">Building Complement</span></span> | <span data-ttu-id="f95f9-739">Linha de endereço 5</span><span class="sxs-lookup"><span data-stu-id="f95f9-739">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="f95f9-740">Número do passaporte</span><span class="sxs-lookup"><span data-stu-id="f95f9-740">Passport number</span></span>

<span data-ttu-id="f95f9-741">Os funcionários podem declarar as informações do passaporte.</span><span class="sxs-lookup"><span data-stu-id="f95f9-741">Employees can declare passport information.</span></span> <span data-ttu-id="f95f9-742">Essas informações são do tipo de identificação **Passaporte** e estão integradas ao Dayforce como parte das informações específicas do México de um funcionário.</span><span class="sxs-lookup"><span data-stu-id="f95f9-742">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="f95f9-743">Tipo de identificação = "Passaporte"</span><span class="sxs-lookup"><span data-stu-id="f95f9-743">Identification Type = "Passport"</span></span>
- <span data-ttu-id="f95f9-744">Data da emissão</span><span class="sxs-lookup"><span data-stu-id="f95f9-744">Issued Date</span></span>
- <span data-ttu-id="f95f9-745">Data de Vencimento</span><span class="sxs-lookup"><span data-stu-id="f95f9-745">Expiration Date</span></span>

<span data-ttu-id="f95f9-746">Os funcionários podem declarar vários números de identificação do tipo de identificação **Passaporte**.</span><span class="sxs-lookup"><span data-stu-id="f95f9-746">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="f95f9-747">No entanto, apenas a entrada atual do passaporte ativo é integrada ao Dayforce.</span><span class="sxs-lookup"><span data-stu-id="f95f9-747">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="f95f9-748">Se todas as entradas do passaporte expirarem, o passaporte emitido mais recentemente será integrado ao Dayforce.</span><span class="sxs-lookup"><span data-stu-id="f95f9-748">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]