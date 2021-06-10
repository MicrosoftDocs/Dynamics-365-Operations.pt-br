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
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6d150daa92fe79cf6620ce5ddf1a01f369c64053
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6051488"
---
# <a name="configure-integration-with-dayforce"></a><span data-ttu-id="5ff79-104">Configurar integração com o Dayforce</span><span class="sxs-lookup"><span data-stu-id="5ff79-104">Configure integration with Dayforce</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="5ff79-105">A integração entre o Microsoft Dynamics 365 Human Resources e o Ceridian Dayforce depende de várias etapas de configuração descritas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="5ff79-105">The integration between Microsoft Dynamics 365 Human Resources and Ceridian Dayforce relies on several configuration steps that are described in this article.</span></span> <span data-ttu-id="5ff79-106">Você deve configurar a integração no Human Resources e no Dayforce antes de processar uma execução de pagamento.</span><span class="sxs-lookup"><span data-stu-id="5ff79-106">You must configure the integration in both Human Resources and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="5ff79-107">Ao usar um serviço como o Dayforce para concluir execuções de pagamento, é necessário ativar a integração no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="5ff79-107">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Human Resources.</span></span> <span data-ttu-id="5ff79-108">A integração requer dados específicos do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="5ff79-108">The integration requires specific data from Human Resources.</span></span> <span data-ttu-id="5ff79-109">Portanto, você deve verificar se os dados mapeados para o Dayforce estão configurados no Human Resources de forma compatível com a integração.</span><span class="sxs-lookup"><span data-stu-id="5ff79-109">Therefore, you must verify that data that is mapped to Dayforce is configured in Human Resources in a manner that supports the integration.</span></span> <span data-ttu-id="5ff79-110">A integração usa as seguintes categorias amplas de dados:</span><span class="sxs-lookup"><span data-stu-id="5ff79-110">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="5ff79-111">Dados de recursos humanos</span><span class="sxs-lookup"><span data-stu-id="5ff79-111">Human resources data</span></span>
- <span data-ttu-id="5ff79-112">Dados de remuneração</span><span class="sxs-lookup"><span data-stu-id="5ff79-112">Compensation data</span></span>
- <span data-ttu-id="5ff79-113">Dados da folha de pagamento, como ciclos de pagamento, períodos de pagamento e códigos de ganhos</span><span class="sxs-lookup"><span data-stu-id="5ff79-113">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="5ff79-114">Dados do trabalhador</span><span class="sxs-lookup"><span data-stu-id="5ff79-114">Worker data</span></span>

<span data-ttu-id="5ff79-115">Este artigo descreve as etapas que você deve seguir para ativar a integração.</span><span class="sxs-lookup"><span data-stu-id="5ff79-115">This article describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="5ff79-116">Também explica os tipos de dados e os detalhes de configuração que a integração requer.</span><span class="sxs-lookup"><span data-stu-id="5ff79-116">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="5ff79-117">Habilitar a integração</span><span class="sxs-lookup"><span data-stu-id="5ff79-117">Enable the integration</span></span>

<span data-ttu-id="5ff79-118">No Human Resources, você deve ativar a integração e inserir as informações de configuração para se conectar ao Dayforce.</span><span class="sxs-lookup"><span data-stu-id="5ff79-118">In Human Resources, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="5ff79-119">Para que a transação de contabilidade produzida seja importada para o Microsoft Dynamics 365 Finance, também é preciso configurar uma conta de armazenamento do Microsoft Azure e inserir a cadeia de conexão do Armazenamento do Azure no Finance.</span><span class="sxs-lookup"><span data-stu-id="5ff79-119">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 Finance, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance.</span></span>

<span data-ttu-id="5ff79-120">Para ativar a integração no Human Resources, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="5ff79-120">To turn on the integration in Human Resources, follow these steps.</span></span>

1. <span data-ttu-id="5ff79-121">Na página **Administração do sistema**, selecione **Configuração de integração**.</span><span class="sxs-lookup"><span data-stu-id="5ff79-121">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="5ff79-122">Digite o ponto de extremidade seguro do File Transfer Protocol (FTP) e o caminho seguro da pasta FTP.</span><span class="sxs-lookup"><span data-stu-id="5ff79-122">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="5ff79-123">Digite o nome e a senha do usuário que acessará o ponto de extremidade e o caminho da pasta seguros do FTP.</span><span class="sxs-lookup"><span data-stu-id="5ff79-123">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="5ff79-124">Teste a conexão, conforme necessário, e defina a opção **Habilitar integração da folha de pagamento** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="5ff79-124">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="5ff79-125">Quando a integração é ativada, o pacote e os arquivos de exportação de dados são criados e a frequência é configurada.</span><span class="sxs-lookup"><span data-stu-id="5ff79-125">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="5ff79-126">Você pode alterar essa frequência conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="5ff79-126">You can change this frequency as you require.</span></span>

<span data-ttu-id="5ff79-127">Para obter mais informações sobre as contas de armazenamento do Azure e as cadeias de conexão do Armazenamento do Azure, consulte os seguintes artigos do Azure:</span><span class="sxs-lookup"><span data-stu-id="5ff79-127">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure articles:</span></span>

- [<span data-ttu-id="5ff79-128">Sobre as contas de armazenamento do Azure</span><span class="sxs-lookup"><span data-stu-id="5ff79-128">About Azure storage accounts</span></span>](/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="5ff79-129">Configurar cadeias de conexão do Armazenamento do Azure</span><span class="sxs-lookup"><span data-stu-id="5ff79-129">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)

### <a name="technical-details-when-payroll-integration-is-enabled"></a><span data-ttu-id="5ff79-130">Detalhes técnicos quando a integração da folha de pagamento está habilitada</span><span class="sxs-lookup"><span data-stu-id="5ff79-130">Technical details when payroll integration is enabled</span></span>

<span data-ttu-id="5ff79-131">A ativação da integração da folha de pagamento tem dois efeitos principais:</span><span class="sxs-lookup"><span data-stu-id="5ff79-131">Turning on the payroll integration has two primary effects:</span></span>

- <span data-ttu-id="5ff79-132">Um projeto de exportação de dados denominado "Exportação de integração da folha de pagamento" é criado.</span><span class="sxs-lookup"><span data-stu-id="5ff79-132">A data export project named "Payroll integration export" is created.</span></span> <span data-ttu-id="5ff79-133">Este projeto contém as entidades e os campos necessários para a integração da folha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="5ff79-133">This project contains the entities and fields required for the payroll integration.</span></span> <span data-ttu-id="5ff79-134">Para revisar o projeto, vá para **Administração do sistema**, selecione o bloco **Gerenciamento de dados** e abra o projeto de dados da lista de projetos.</span><span class="sxs-lookup"><span data-stu-id="5ff79-134">To examine the project, go to **System administration**, select the **Data management** tile, and then open the data project from the list of projects.</span></span>
- <span data-ttu-id="5ff79-135">Esse trabalho em lotes executa o projeto de exportação de dados, criptografa o pacote de dados resultante e transfere o arquivo do pacote de dados para a empresa de SFTP configurada na tela **Configuração de integração**.</span><span class="sxs-lookup"><span data-stu-id="5ff79-135">This batch job executes the data export project, encrypts the resulting data package, and transfers the data package file to the SFTP endpoint configured on the **Integration configuration** screen.</span></span>

> [!NOTE]
> <span data-ttu-id="5ff79-136">O pacote de dados transferido para a empresa de SFTP é criptografado usando uma chave exclusiva para o pacote.</span><span class="sxs-lookup"><span data-stu-id="5ff79-136">The data package transferred to the SFTP endpoint is encrypted using a key that is unique to the package.</span></span> <span data-ttu-id="5ff79-137">A chave é um Azure Key Vault acessível somente pelo Ceridian.</span><span class="sxs-lookup"><span data-stu-id="5ff79-137">The key is in an Azure Key Vault that is accessible only by Ceridian.</span></span> <span data-ttu-id="5ff79-138">Não é possível descriptografar e revisar o conteúdo do pacote de dados.</span><span class="sxs-lookup"><span data-stu-id="5ff79-138">It is not possible to decrypt and examine the data package contents.</span></span> <span data-ttu-id="5ff79-139">Se você precisar examinar o conteúdo do pacote de dados, exporte manualmente o projeto de dados "Exportação de integração da folha de pagamento", baixe-o e abra-o</span><span class="sxs-lookup"><span data-stu-id="5ff79-139">If you need to examine the contents of the data package, you need to export the "Payroll integration export" data project manually, download it, and then open it.</span></span> <span data-ttu-id="5ff79-140">A exportação manual não aplicará a criptografia nem transferirá o pacote.</span><span class="sxs-lookup"><span data-stu-id="5ff79-140">Manual export will not apply encryption or transfer the package.</span></span>
> <span data-ttu-id="5ff79-141">Para instâncias em que os arquivos de integração são enviados de um ambiente de UAT ou de área restrita do Dynamics 365 Human Resources para um ambiente de teste Ceridian Dayforce, você pode usar a seguinte URL do cofre de chaves: https://payrollintegrationprod.vault.azure.net.</span><span class="sxs-lookup"><span data-stu-id="5ff79-141">For instances where the integration files are sent from a Dynamics 365 Human Resources UAT or Sandbox environment to a Ceridian Dayforce Test environment, you can use the following key vault URL: https://payrollintegrationprod.vault.azure.net.</span></span>

## <a name="configure-your-data"></a><span data-ttu-id="5ff79-142">Configurar seus dados</span><span class="sxs-lookup"><span data-stu-id="5ff79-142">Configure your data</span></span> 

<span data-ttu-id="5ff79-143">Para processar a folha de pagamento, você deve configurar dados de RH no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="5ff79-143">To process payroll, you must configure human resource data in Human Resources.</span></span> <span data-ttu-id="5ff79-144">Você deve configurar dados organizacionais, como cargos e posições, juntamente com informações sobre benefícios e remuneração.</span><span class="sxs-lookup"><span data-stu-id="5ff79-144">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="5ff79-145">Esses dados fornecem as informações de emprego, pagamento e dedução necessárias para gerar o pagamento do empregado.</span><span class="sxs-lookup"><span data-stu-id="5ff79-145">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="5ff79-146">Dados de RH</span><span class="sxs-lookup"><span data-stu-id="5ff79-146">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="5ff79-147">Benefícios</span><span class="sxs-lookup"><span data-stu-id="5ff79-147">Benefits</span></span> 

<span data-ttu-id="5ff79-148">O RH fornece ferramentas para a configuração e manutenção dos benefícios, deduções e planos de remuneração do trabalhador que uma organização oferece ou processa para seus funcionários.</span><span class="sxs-lookup"><span data-stu-id="5ff79-148">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="5ff79-149">Ao criar benefícios, tenha em mente os dados e configurações a seguir usados no Dayforce.</span><span class="sxs-lookup"><span data-stu-id="5ff79-149">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="5ff79-150">Planos de benefícios</span><span class="sxs-lookup"><span data-stu-id="5ff79-150">Benefit plans</span></span>

- <span data-ttu-id="5ff79-151">Plano (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-151">Plan (required)</span></span>
- <span data-ttu-id="5ff79-152">Tipo (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-152">Type (required)</span></span>
- <span data-ttu-id="5ff79-153">Impacto da folha de pagamento (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-153">Payroll impact (required)</span></span>
- <span data-ttu-id="5ff79-154">Recuperar atrasos de pagamento</span><span class="sxs-lookup"><span data-stu-id="5ff79-154">Recover arrears</span></span>
- <span data-ttu-id="5ff79-155">Método de dedução</span><span class="sxs-lookup"><span data-stu-id="5ff79-155">Deduction method</span></span>
- <span data-ttu-id="5ff79-156">Prioridade da dedução</span><span class="sxs-lookup"><span data-stu-id="5ff79-156">Deduction priority</span></span>
- <span data-ttu-id="5ff79-157">Limitar período</span><span class="sxs-lookup"><span data-stu-id="5ff79-157">Limit period</span></span>
- <span data-ttu-id="5ff79-158">Valor de limite</span><span class="sxs-lookup"><span data-stu-id="5ff79-158">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="5ff79-159">Benefícios</span><span class="sxs-lookup"><span data-stu-id="5ff79-159">Benefits</span></span>

- <span data-ttu-id="5ff79-160">Plano (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-160">Plan (required)</span></span>
- <span data-ttu-id="5ff79-161">Tipo (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-161">Type (required)</span></span>
- <span data-ttu-id="5ff79-162">Opção (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="5ff79-162">Option (required)</span></span>
- <span data-ttu-id="5ff79-163">ID do benefício (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="5ff79-163">Benefit ID (required)</span></span>
- <span data-ttu-id="5ff79-164">Frequência</span><span class="sxs-lookup"><span data-stu-id="5ff79-164">Frequency</span></span>
- <span data-ttu-id="5ff79-165">Base</span><span class="sxs-lookup"><span data-stu-id="5ff79-165">Basis</span></span>
- <span data-ttu-id="5ff79-166">Valor ou taxa</span><span class="sxs-lookup"><span data-stu-id="5ff79-166">Amount or rate</span></span>
- <span data-ttu-id="5ff79-167">Código de ganhos</span><span class="sxs-lookup"><span data-stu-id="5ff79-167">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="5ff79-168">Frequências com suporte</span><span class="sxs-lookup"><span data-stu-id="5ff79-168">Supported frequencies</span></span> 

- <span data-ttu-id="5ff79-169">Semanalmente</span><span class="sxs-lookup"><span data-stu-id="5ff79-169">Weekly</span></span>
- <span data-ttu-id="5ff79-170">Por quinzena</span><span class="sxs-lookup"><span data-stu-id="5ff79-170">Bi-weekly</span></span>
- <span data-ttu-id="5ff79-171">Quinzenal</span><span class="sxs-lookup"><span data-stu-id="5ff79-171">Semi-monthly</span></span>
- <span data-ttu-id="5ff79-172">Mensalmente</span><span class="sxs-lookup"><span data-stu-id="5ff79-172">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="5ff79-173">Bases com suporte</span><span class="sxs-lookup"><span data-stu-id="5ff79-173">Supported bases</span></span> 

- <span data-ttu-id="5ff79-174">Valor fixo</span><span class="sxs-lookup"><span data-stu-id="5ff79-174">Fixed amount</span></span>
- <span data-ttu-id="5ff79-175">Percentual de ganhos</span><span class="sxs-lookup"><span data-stu-id="5ff79-175">Percent of earnings</span></span>
- <span data-ttu-id="5ff79-176">Horas produtivas</span><span class="sxs-lookup"><span data-stu-id="5ff79-176">Productive hours</span></span>

<span data-ttu-id="5ff79-177">O Dayforce cria as deduções a seguir, com base no impacto da folha de pagamento definido no plano de benefícios.</span><span class="sxs-lookup"><span data-stu-id="5ff79-177">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="5ff79-178">Seleção no Human Resources</span><span class="sxs-lookup"><span data-stu-id="5ff79-178">Selection in Human Resources</span></span>        | <span data-ttu-id="5ff79-179">Resultado no Dayforce</span><span class="sxs-lookup"><span data-stu-id="5ff79-179">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="5ff79-180">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="5ff79-180">None</span></span>                       | <span data-ttu-id="5ff79-181">Nenhuma dedução é criada.</span><span class="sxs-lookup"><span data-stu-id="5ff79-181">No deduction is created.</span></span>                      |
| <span data-ttu-id="5ff79-182">Somente dedução</span><span class="sxs-lookup"><span data-stu-id="5ff79-182">Deduction only</span></span>             | <span data-ttu-id="5ff79-183">Uma dedução de funcionário é criada.</span><span class="sxs-lookup"><span data-stu-id="5ff79-183">An employee deduction is created.</span></span>             |
| <span data-ttu-id="5ff79-184">Somente contribuição</span><span class="sxs-lookup"><span data-stu-id="5ff79-184">Contribution only</span></span>          | <span data-ttu-id="5ff79-185">Uma dedução de empregador é criada.</span><span class="sxs-lookup"><span data-stu-id="5ff79-185">An employer deduction is created.</span></span>             |
| <span data-ttu-id="5ff79-186">Dedução e contribuição</span><span class="sxs-lookup"><span data-stu-id="5ff79-186">Deduction and contribution</span></span> | <span data-ttu-id="5ff79-187">Deduções de funcionário e empregador são criadas.</span><span class="sxs-lookup"><span data-stu-id="5ff79-187">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="5ff79-188">Para obter mais informações sobre como definir e gerenciar um programa de benefícios, consulte os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="5ff79-188">For more information about how to define and manage a benefits program, see the following articles:</span></span>

- [<span data-ttu-id="5ff79-189">Entregar um programa de benefícios para funcionários</span><span class="sxs-lookup"><span data-stu-id="5ff79-189">Deliver an employee benefits program</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="5ff79-190">Criar um novo benefício</span><span class="sxs-lookup"><span data-stu-id="5ff79-190">Create a new benefit</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="5ff79-191">Definir regras e políticas de qualificação para o benefício</span><span class="sxs-lookup"><span data-stu-id="5ff79-191">Define benefit eligibility rules and policies</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="5ff79-192">Inscrever e remover benefícios de trabalhadores</span><span class="sxs-lookup"><span data-stu-id="5ff79-192">Enroll and remove benefits from workers</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="5ff79-193">Remuneração</span><span class="sxs-lookup"><span data-stu-id="5ff79-193">Compensation</span></span> 

<span data-ttu-id="5ff79-194">O gerenciamento de remuneração é usado para controlar o pagamento do salário base e de prêmios.</span><span class="sxs-lookup"><span data-stu-id="5ff79-194">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="5ff79-195">Os aumentos no salário base fixo e nos prêmios de um funcionário são controlados por meio de planos de remuneração fixos.</span><span class="sxs-lookup"><span data-stu-id="5ff79-195">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="5ff79-196">O pagamento de incentivos, como pagamentos de bônus, prêmios por desempenho, opções de ação e concessões, além de prêmios únicos, são controlados por meio de planos de remuneração variável.</span><span class="sxs-lookup"><span data-stu-id="5ff79-196">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="5ff79-197">O Dayforce usa informações de remuneração para calcular a taxa por hora ou anual de um funcionário.</span><span class="sxs-lookup"><span data-stu-id="5ff79-197">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="5ff79-198">Planos de remuneração fixa e conversões de taxa de pagamento são necessários.</span><span class="sxs-lookup"><span data-stu-id="5ff79-198">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="5ff79-199">Os funcionários devem estar associados a um plano de remuneração fixa.</span><span class="sxs-lookup"><span data-stu-id="5ff79-199">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="5ff79-200">Para obter mais informações sobre planos de compensação, veja os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="5ff79-200">For more information about compensation plans, see the following articles:</span></span>

- [<span data-ttu-id="5ff79-201">Criar planos de remuneração fixa</span><span class="sxs-lookup"><span data-stu-id="5ff79-201">Create fixed compensation plans</span></span>](/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="5ff79-202">Criar planos de remuneração variável</span><span class="sxs-lookup"><span data-stu-id="5ff79-202">Create variable compensation plans</span></span>](/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="5ff79-203">Desenvolver estrutura e planos de remuneração/salário</span><span class="sxs-lookup"><span data-stu-id="5ff79-203">Develop salary/compensation structure and plans</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="5ff79-204">Processar remuneração</span><span class="sxs-lookup"><span data-stu-id="5ff79-204">Process compensation</span></span>](/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="5ff79-205">Definir processo de remuneração e calcular resultados</span><span class="sxs-lookup"><span data-stu-id="5ff79-205">Define compensation process and calculate results</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="5ff79-206">Inscrever um funcionário em um plano de remuneração fixa</span><span class="sxs-lookup"><span data-stu-id="5ff79-206">Enroll an employee in a fixed compensation plan</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="5ff79-207">Inscrever um funcionário em um plano de remuneração variável</span><span class="sxs-lookup"><span data-stu-id="5ff79-207">Enroll an employee in a variable compensation plan</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="5ff79-208">Trabalhos</span><span class="sxs-lookup"><span data-stu-id="5ff79-208">Jobs</span></span> 

<span data-ttu-id="5ff79-209">Um trabalho é um conjunto de tarefas e responsabilidades exigidas de uma pessoa que realiza um trabalho.</span><span class="sxs-lookup"><span data-stu-id="5ff79-209">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="5ff79-210">Para obter mais informações, consulte os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="5ff79-210">For more information, see the following articles:</span></span>

- [<span data-ttu-id="5ff79-211">Configurando os componentes de um trabalho</span><span class="sxs-lookup"><span data-stu-id="5ff79-211">Setting up the components of a job</span></span>](/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="5ff79-212">Definir novos trabalhos</span><span class="sxs-lookup"><span data-stu-id="5ff79-212">Define new jobs</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="5ff79-213">Cargos</span><span class="sxs-lookup"><span data-stu-id="5ff79-213">Positions</span></span>

<span data-ttu-id="5ff79-214">Um cargo é uma instância individual de um trabalho.</span><span class="sxs-lookup"><span data-stu-id="5ff79-214">A position is an individual instance of a job.</span></span> <span data-ttu-id="5ff79-215">Por exemplo, a posição "Gerente de vendas (Leste)" é uma das posições associadas ao trabalho "Gerente de vendas".</span><span class="sxs-lookup"><span data-stu-id="5ff79-215">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="5ff79-216">Uma posição existe em um departamento.</span><span class="sxs-lookup"><span data-stu-id="5ff79-216">A position exists in a department.</span></span> <span data-ttu-id="5ff79-217">Apenas um trabalhador pode ser associado a cada posição.</span><span class="sxs-lookup"><span data-stu-id="5ff79-217">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="5ff79-218">Considere os seguintes dados e configurações ao configurar as posições:</span><span class="sxs-lookup"><span data-stu-id="5ff79-218">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="5ff79-219">Posição (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="5ff79-219">Position (required)</span></span>
- <span data-ttu-id="5ff79-220">Descrição (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="5ff79-220">Description (required)</span></span>
- <span data-ttu-id="5ff79-221">Trabalho (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-221">Job (required)</span></span>
- <span data-ttu-id="5ff79-222">Departamento (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-222">Department (required)</span></span>
- <span data-ttu-id="5ff79-223">Tipo de posição (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-223">Position type (required)</span></span>
- <span data-ttu-id="5ff79-224">Equivalente ao horário integral</span><span class="sxs-lookup"><span data-stu-id="5ff79-224">Full-time equivalent</span></span>
- <span data-ttu-id="5ff79-225">Horas normais anuais (obrigatórias)</span><span class="sxs-lookup"><span data-stu-id="5ff79-225">Annual regular hours (required)</span></span>
- <span data-ttu-id="5ff79-226">Pago por entidade legal (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-226">Paid by legal entity (required)</span></span>
- <span data-ttu-id="5ff79-227">Ciclo de pagamento (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-227">Pay cycle (required)</span></span>
- <span data-ttu-id="5ff79-228">Dimensão financeira padrão – Centro de custo (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-228">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="5ff79-229">Atribuição do trabalhador – Trabalhador, início da atribuição, fim da atribuição, código de motivo</span><span class="sxs-lookup"><span data-stu-id="5ff79-229">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="5ff79-230">Se várias posições no mesmo departamento estiverem associadas ao mesmo trabalho, elas serão consolidadas em uma única posição no Dayforce.</span><span class="sxs-lookup"><span data-stu-id="5ff79-230">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="5ff79-231">Para obter mais informações, consulte os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="5ff79-231">For more information, see the following articles:</span></span>

- [<span data-ttu-id="5ff79-232">Organizar sua força de trabalho usando departamentos, trabalhos e posições</span><span class="sxs-lookup"><span data-stu-id="5ff79-232">Organize your workforce using departments, jobs, and positions</span></span>](/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="5ff79-233">Configurar posições</span><span class="sxs-lookup"><span data-stu-id="5ff79-233">Set up positions</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="5ff79-234">Departamentos</span><span class="sxs-lookup"><span data-stu-id="5ff79-234">Departments</span></span>

<span data-ttu-id="5ff79-235">Um departamento é uma unidade operacional que representa uma categoria ou uma área funcional de uma organização.</span><span class="sxs-lookup"><span data-stu-id="5ff79-235">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="5ff79-236">Um departamento é responsável por uma área específica da organização, como vendas, contabilidade ou recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="5ff79-236">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="5ff79-237">Você pode usar departamentos para relatar áreas funcionais.</span><span class="sxs-lookup"><span data-stu-id="5ff79-237">You can use departments to report on functional areas.</span></span> <span data-ttu-id="5ff79-238">Os departamentos podem ter a responsabilidade de lucros e perdas.</span><span class="sxs-lookup"><span data-stu-id="5ff79-238">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="5ff79-239">Para obter mais informações, consulte os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="5ff79-239">For more information, see the following articles:</span></span>

- [<span data-ttu-id="5ff79-240">Criar um departamento e associá-lo à hierarquia de departamentos</span><span class="sxs-lookup"><span data-stu-id="5ff79-240">Create a department and associate it with the department hierarchy</span></span>](/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="5ff79-241">Definir novos departamentos</span><span class="sxs-lookup"><span data-stu-id="5ff79-241">Define new departments</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="5ff79-242">Ciclos de pagamento e períodos de pagamento</span><span class="sxs-lookup"><span data-stu-id="5ff79-242">Pay cycles and pay periods</span></span>

<span data-ttu-id="5ff79-243">Um ciclo de pagamento determina a frequência com que a folha de pagamento é executada e os dias específicos em que os trabalhadores são pagos.</span><span class="sxs-lookup"><span data-stu-id="5ff79-243">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="5ff79-244">Por exemplo, um ciclo de pagamento pode ser mensal e os funcionários podem ser pagos no último dia do mês.</span><span class="sxs-lookup"><span data-stu-id="5ff79-244">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="5ff79-245">Como alternativa, um ciclo de pagamento pode ser semanal e os funcionários podem ser pagos na terça-feira após o término do período de pagamento.</span><span class="sxs-lookup"><span data-stu-id="5ff79-245">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="5ff79-246">Ciclos de pagamento são atribuídos a posições para controlar quando os trabalhadores nessas posições são pagos.</span><span class="sxs-lookup"><span data-stu-id="5ff79-246">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="5ff79-247">Após a criação dos ciclos de pagamento, você pode gerar períodos de pagamento para cada ciclo.</span><span class="sxs-lookup"><span data-stu-id="5ff79-247">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="5ff79-248">Cada período de pagamento inclui uma data de pagamento padrão baseada nas informações que você fornece.</span><span class="sxs-lookup"><span data-stu-id="5ff79-248">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="5ff79-249">No entanto, você pode modificar a data de pagamento padrão em um período de pagamento para permitir exceções (por exemplo, quando a data de pagamento cai em um feriado).</span><span class="sxs-lookup"><span data-stu-id="5ff79-249">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="5ff79-250">As seguintes informações são usadas no Dayforce:</span><span class="sxs-lookup"><span data-stu-id="5ff79-250">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="5ff79-251">Ciclo de pagamento (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-251">Pay cycle (required)</span></span>
- <span data-ttu-id="5ff79-252">Frequência do ciclo de pagamento (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="5ff79-252">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="5ff79-253">Data de início do período (primeiro período de pagamento obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-253">Period start date (first pay period required)</span></span>
- <span data-ttu-id="5ff79-254">Data de pagamento padrão (primeiro período de pagamento obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-254">Default payment date (first pay period required)</span></span>

<span data-ttu-id="5ff79-255">Essas informações são integradas ao Dayforce como grupos de pagamento e são separadas por país ou região para cada ciclo de pagamento.</span><span class="sxs-lookup"><span data-stu-id="5ff79-255">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="5ff79-256">Pelo menos um período de pagamento deve ser gerado antes da integração.</span><span class="sxs-lookup"><span data-stu-id="5ff79-256">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="5ff79-257">O Dayforce gera datas de pagamento e calendários do grupo de pagamento, com base na data de início do primeiro período de pagamento e na data de pagamento padrão configurada no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="5ff79-257">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Human Resources.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="5ff79-258">Códigos de ganhos</span><span class="sxs-lookup"><span data-stu-id="5ff79-258">Earning codes</span></span>

<span data-ttu-id="5ff79-259">Os códigos de ganhos identificam de forma exclusiva cada tipo de ganho que os trabalhadores recebem.</span><span class="sxs-lookup"><span data-stu-id="5ff79-259">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="5ff79-260">Os códigos têm vários parâmetros relacionados a ganhos, como regras contábeis, leis tributárias, requisitos de relatório e capacidade de montante bruto.</span><span class="sxs-lookup"><span data-stu-id="5ff79-260">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="5ff79-261">As seguintes informações são usadas no Dayforce:</span><span class="sxs-lookup"><span data-stu-id="5ff79-261">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="5ff79-262">Código de ganhos (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-262">Earning Code (required)</span></span>
- <span data-ttu-id="5ff79-263">descrição</span><span class="sxs-lookup"><span data-stu-id="5ff79-263">Description</span></span>
- <span data-ttu-id="5ff79-264">Unidade de medida</span><span class="sxs-lookup"><span data-stu-id="5ff79-264">Unit of measure</span></span>
- <span data-ttu-id="5ff79-265">Produtivo</span><span class="sxs-lookup"><span data-stu-id="5ff79-265">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="5ff79-266">Dados do trabalhador</span><span class="sxs-lookup"><span data-stu-id="5ff79-266">Worker data</span></span>

<span data-ttu-id="5ff79-267">Os registros dos vários tipos de trabalhadores que você tem são importantes para o RH e sistemas de folha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="5ff79-267">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="5ff79-268">As informações inseridas podem ser usadas para rastrear trabalhadores e informações pessoais.</span><span class="sxs-lookup"><span data-stu-id="5ff79-268">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="5ff79-269">Você pode manter estas informações para trabalhadores:</span><span class="sxs-lookup"><span data-stu-id="5ff79-269">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="5ff79-270">**Básicas** – mantenha informações básicas do trabalhador, como informações de contato, demográficas, de identificação, sobre a família, o status de serviço militar, informações de exilado, contatos pessoais e de emergência.</span><span class="sxs-lookup"><span data-stu-id="5ff79-270">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="5ff79-271">**Emprego** – mantenha informações sobre o emprego dos trabalhadores, como a afiliação da empresa ou organização, a atribuição de posição, as datas inicial e final, a qualificação para trabalho, o contrato de trabalho, a pensão, férias e as informações de mudança.</span><span class="sxs-lookup"><span data-stu-id="5ff79-271">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="5ff79-272">**Licença e ausência** – mantenha informações sobre as ausências dos trabalhadores, como o calendário de trabalho, as transações de ausência e a configuração de ausência.</span><span class="sxs-lookup"><span data-stu-id="5ff79-272">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="5ff79-273">**Remuneração e folha de pagamento** – mantenha informações sobre os planos de remuneração e as informações de folha de pagamento de trabalhadores, como o registro do plano, prêmios, o desempenho, a comissão, informações sobre impostos, aposentadoria e deduções do salário.</span><span class="sxs-lookup"><span data-stu-id="5ff79-273">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="5ff79-274">Ao inserir informações do trabalhador, tenha em mente os dados e configurações a seguir usados no Dayforce.</span><span class="sxs-lookup"><span data-stu-id="5ff79-274">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="5ff79-275">Informações gerais</span><span class="sxs-lookup"><span data-stu-id="5ff79-275">General information</span></span>

- <span data-ttu-id="5ff79-276">Número de equipe (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-276">Personnel number (required)</span></span>
- <span data-ttu-id="5ff79-277">Nome (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-277">First name (required)</span></span>
- <span data-ttu-id="5ff79-278">Sobrenome (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-278">Last name (required)</span></span>
- <span data-ttu-id="5ff79-279">Nome do meio</span><span class="sxs-lookup"><span data-stu-id="5ff79-279">Middle name</span></span>
- <span data-ttu-id="5ff79-280">Aniversário de tempo de serviço</span><span class="sxs-lookup"><span data-stu-id="5ff79-280">Seniority date</span></span>
- <span data-ttu-id="5ff79-281">Conhecido como</span><span class="sxs-lookup"><span data-stu-id="5ff79-281">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="5ff79-282">Informações pessoais</span><span class="sxs-lookup"><span data-stu-id="5ff79-282">Personal information</span></span>

- <span data-ttu-id="5ff79-283">Estado civil (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-283">Marital status (required)</span></span>
- <span data-ttu-id="5ff79-284">Data de nascimento (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="5ff79-284">Birth date (required)</span></span>
- <span data-ttu-id="5ff79-285">Sexo (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-285">Gender (required)</span></span>
- <span data-ttu-id="5ff79-286">Pessoa portadora de deficiências</span><span class="sxs-lookup"><span data-stu-id="5ff79-286">Person with disabilities</span></span>
- <span data-ttu-id="5ff79-287">Região do país de nacionalidade (somente para o México)</span><span class="sxs-lookup"><span data-stu-id="5ff79-287">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="5ff79-288">Informações de endereço</span><span class="sxs-lookup"><span data-stu-id="5ff79-288">Address information</span></span>

- <span data-ttu-id="5ff79-289">Principal (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-289">Primary (required)</span></span>
- <span data-ttu-id="5ff79-290">País/região (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-290">Country/region (required)</span></span>
- <span data-ttu-id="5ff79-291">CEP (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-291">Postal code (required)</span></span>
- <span data-ttu-id="5ff79-292">Número da rua (obrigatório) (somente para o México)</span><span class="sxs-lookup"><span data-stu-id="5ff79-292">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="5ff79-293">Complemento do edifício (somente para o México)</span><span class="sxs-lookup"><span data-stu-id="5ff79-293">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="5ff79-294">Cidade (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="5ff79-294">City (required)</span></span>
- <span data-ttu-id="5ff79-295">Estado (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-295">State (required)</span></span>
- <span data-ttu-id="5ff79-296">Município (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-296">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="5ff79-297">Informações de contato</span><span class="sxs-lookup"><span data-stu-id="5ff79-297">Contact information</span></span> 

- <span data-ttu-id="5ff79-298">Principal (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-298">Primary (required)</span></span>
- <span data-ttu-id="5ff79-299">Número de contato (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-299">Contact number (required)</span></span>
- <span data-ttu-id="5ff79-300">Extensão</span><span class="sxs-lookup"><span data-stu-id="5ff79-300">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="5ff79-301">Informações sobre folha de pagamento e códigos de ganhos</span><span class="sxs-lookup"><span data-stu-id="5ff79-301">Payroll information and earning codes</span></span>

<span data-ttu-id="5ff79-302">Os funcionários podem receber ganhos específicos com uma determinada frequência de pagamento e ter um método de pagamento preferencial.</span><span class="sxs-lookup"><span data-stu-id="5ff79-302">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="5ff79-303">Os campos a seguir são usados no Dayforce para ajudar a garantir que essas preferências e configurações sejam usadas.</span><span class="sxs-lookup"><span data-stu-id="5ff79-303">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="5ff79-304">Códigos de ganhos</span><span class="sxs-lookup"><span data-stu-id="5ff79-304">Earning codes</span></span>

- <span data-ttu-id="5ff79-305">Posição (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="5ff79-305">Position (required)</span></span>
- <span data-ttu-id="5ff79-306">Código de ganhos (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-306">Earning Code (required)</span></span>
- <span data-ttu-id="5ff79-307">Frequência (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="5ff79-307">Frequency (required)</span></span>
- <span data-ttu-id="5ff79-308">Valor (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-308">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="5ff79-309">Informações da folha de pagamento</span><span class="sxs-lookup"><span data-stu-id="5ff79-309">Payroll information</span></span>

- <span data-ttu-id="5ff79-310">Método de Pagamento</span><span class="sxs-lookup"><span data-stu-id="5ff79-310">Payment Method</span></span>
- <span data-ttu-id="5ff79-311">Região econômica (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="5ff79-311">Economic Region (required)</span></span>
- <span data-ttu-id="5ff79-312">ID de Benefícios do Funcionário</span><span class="sxs-lookup"><span data-stu-id="5ff79-312">Employee Benefits ID</span></span>
- <span data-ttu-id="5ff79-313">Número de ID nacional (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-313">National ID Number (required)</span></span>
- <span data-ttu-id="5ff79-314">Número de serviço militar</span><span class="sxs-lookup"><span data-stu-id="5ff79-314">Military Service Number</span></span>
- <span data-ttu-id="5ff79-315">ID de turno (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="5ff79-315">Shift ID (required)</span></span>
- <span data-ttu-id="5ff79-316">Número fiscal (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-316">Tax Number (required)</span></span>
- <span data-ttu-id="5ff79-317">ID do sindicato (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="5ff79-317">Union ID (required)</span></span>
- <span data-ttu-id="5ff79-318">ID do dia útil (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="5ff79-318">Work Day ID (required)</span></span>
- <span data-ttu-id="5ff79-319">Número de autorização de trabalho</span><span class="sxs-lookup"><span data-stu-id="5ff79-319">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="5ff79-320">Para o método de pagamento, o México permite **Pagamento à vista**, **Cheque** (o cheque físico da empresa) e **Pagamento Eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="5ff79-320">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="5ff79-321">Se nenhum método de pagamento for especificado, **Cheque** é usado por padrão.</span><span class="sxs-lookup"><span data-stu-id="5ff79-321">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="5ff79-322">Detalhes do emprego</span><span class="sxs-lookup"><span data-stu-id="5ff79-322">Employment details</span></span>

<span data-ttu-id="5ff79-323">O histórico de detalhes de emprego é usado como principal informação para derivar os status de contratação, rescisão e recontratação de um funcionário no Dayforce.</span><span class="sxs-lookup"><span data-stu-id="5ff79-323">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="5ff79-324">O Dayforce suporta apenas um registro de emprego ativo de cada vez.</span><span class="sxs-lookup"><span data-stu-id="5ff79-324">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="5ff79-325">Data de início do emprego (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="5ff79-325">Employment start date (required)</span></span>
- <span data-ttu-id="5ff79-326">Data final do emprego</span><span class="sxs-lookup"><span data-stu-id="5ff79-326">Employment end date</span></span>
- <span data-ttu-id="5ff79-327">Data de início</span><span class="sxs-lookup"><span data-stu-id="5ff79-327">Start date</span></span>
- <span data-ttu-id="5ff79-328">Data inicial ajustada</span><span class="sxs-lookup"><span data-stu-id="5ff79-328">Adjusted start date</span></span>
- <span data-ttu-id="5ff79-329">Data de rescisão (obrigatória após a rescisão)</span><span class="sxs-lookup"><span data-stu-id="5ff79-329">Termination date (required upon termination)</span></span>
- <span data-ttu-id="5ff79-330">Motivo da rescisão (obrigatória após a rescisão)</span><span class="sxs-lookup"><span data-stu-id="5ff79-330">Termination reason (required upon termination)</span></span>

<span data-ttu-id="5ff79-331">As principais datas de um funcionário são derivadas usando-se as informações a seguir.</span><span class="sxs-lookup"><span data-stu-id="5ff79-331">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="5ff79-332">Recursos Humanos</span><span class="sxs-lookup"><span data-stu-id="5ff79-332">Human Resources</span></span>                | <span data-ttu-id="5ff79-333">Dayforce</span><span class="sxs-lookup"><span data-stu-id="5ff79-333">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="5ff79-334">Data de contratação mais recente</span><span class="sxs-lookup"><span data-stu-id="5ff79-334">Most recent hire date</span></span> | <span data-ttu-id="5ff79-335">Início de emprego do registro histórico de emprego atual não terminado</span><span class="sxs-lookup"><span data-stu-id="5ff79-335">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="5ff79-336">Data da rescisão</span><span class="sxs-lookup"><span data-stu-id="5ff79-336">Termination date</span></span>      | <span data-ttu-id="5ff79-337">Data de rescisão do registro histórico de emprego atual não terminado</span><span class="sxs-lookup"><span data-stu-id="5ff79-337">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="5ff79-338">Data de início</span><span class="sxs-lookup"><span data-stu-id="5ff79-338">Start date</span></span>            | <span data-ttu-id="5ff79-339">Data de início ajustada, data de início ou início de emprego do registro histórico de emprego não ativo atual</span><span class="sxs-lookup"><span data-stu-id="5ff79-339">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="5ff79-340">Data original de contratação</span><span class="sxs-lookup"><span data-stu-id="5ff79-340">Original hire date</span></span>    | <span data-ttu-id="5ff79-341">Início de emprego do registro histórico de emprego mais antigo</span><span class="sxs-lookup"><span data-stu-id="5ff79-341">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="5ff79-342">Remuneração</span><span class="sxs-lookup"><span data-stu-id="5ff79-342">Compensation</span></span>

<span data-ttu-id="5ff79-343">Um plano de remuneração fixa deve estar associado à posição principal de cada funcionário durante um período de emprego.</span><span class="sxs-lookup"><span data-stu-id="5ff79-343">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="5ff79-344">Esse período tem início na data em que o funcionário foi contratado (ou na data de início do emprego) e continua até a rescisão.</span><span class="sxs-lookup"><span data-stu-id="5ff79-344">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="5ff79-345">Data de vigência (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="5ff79-345">Effective Date (required)</span></span>
- <span data-ttu-id="5ff79-346">Data de vencimento</span><span class="sxs-lookup"><span data-stu-id="5ff79-346">Expiration date</span></span>
- <span data-ttu-id="5ff79-347">Taxa de pagamento (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="5ff79-347">Pay Rate (required)</span></span>
- <span data-ttu-id="5ff79-348">Conversões de taxa de pagamento (obrigatórias)</span><span class="sxs-lookup"><span data-stu-id="5ff79-348">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="5ff79-349">Equivalente anual (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-349">Annual equivalent (required)</span></span>
- <span data-ttu-id="5ff79-350">Equivalente por hora (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-350">Hourly equivalent (required)</span></span>

<span data-ttu-id="5ff79-351">Se um funcionário por hora tiver várias posições, a remuneração fixa da posição principal é importada para o Dayforce como a taxa base/salário do nível do funcionário.</span><span class="sxs-lookup"><span data-stu-id="5ff79-351">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="5ff79-352">Para posições não principais, a taxa por hora é salva na posição correspondente no Dayforce.</span><span class="sxs-lookup"><span data-stu-id="5ff79-352">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="5ff79-353">Se um funcionário assalariado tiver várias posições, a taxa acumulada de horas e o salário anual em todas as posições ativas serão derivados e usados como a taxa base/salário do nível do funcionário.</span><span class="sxs-lookup"><span data-stu-id="5ff79-353">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="5ff79-354">Números de identificação</span><span class="sxs-lookup"><span data-stu-id="5ff79-354">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="5ff79-355">Cadastro de Pessoa Física (CPF)</span><span class="sxs-lookup"><span data-stu-id="5ff79-355">Social Security identifier</span></span> 

<span data-ttu-id="5ff79-356">Todos os funcionários devem ter um identificador principal.</span><span class="sxs-lookup"><span data-stu-id="5ff79-356">Every employee must have one primary identifier.</span></span> <span data-ttu-id="5ff79-357">Esse identificador deve ser o tipo de identificação **CPF**.</span><span class="sxs-lookup"><span data-stu-id="5ff79-357">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="5ff79-358">No Dayforce, ele é derivado automaticamente como o identificador de pessoa física do funcionário necessário para a contratação.</span><span class="sxs-lookup"><span data-stu-id="5ff79-358">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="5ff79-359">Principal (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-359">Primary (required)</span></span>
- <span data-ttu-id="5ff79-360">Tipo de identificação = "CPF"</span><span class="sxs-lookup"><span data-stu-id="5ff79-360">Identification Type = "SSN"</span></span>
- <span data-ttu-id="5ff79-361">Data da emissão</span><span class="sxs-lookup"><span data-stu-id="5ff79-361">Issued Date</span></span>
- <span data-ttu-id="5ff79-362">Data de Vencimento</span><span class="sxs-lookup"><span data-stu-id="5ff79-362">Expiration Date</span></span>

<span data-ttu-id="5ff79-363">Os funcionários podem declarar vários números de identificação do tipo de identificação **CPF**.</span><span class="sxs-lookup"><span data-stu-id="5ff79-363">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="5ff79-364">No entanto, somente o registro marcado como **Principal** será integrado ao Dayforce, independentemente de o número estar ativo ou expirado.</span><span class="sxs-lookup"><span data-stu-id="5ff79-364">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="5ff79-365">Contas bancárias e pagamentos</span><span class="sxs-lookup"><span data-stu-id="5ff79-365">Bank accounts and disbursements</span></span>

<span data-ttu-id="5ff79-366">Informações de conta bancária válidas devem ser inseridas para qualquer funcionário que opte por ser pago por meio de transferências bancárias.</span><span class="sxs-lookup"><span data-stu-id="5ff79-366">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="5ff79-367">Recursos Humanos</span><span class="sxs-lookup"><span data-stu-id="5ff79-367">Human Resources</span></span>                         | <span data-ttu-id="5ff79-368">Dayforce</span><span class="sxs-lookup"><span data-stu-id="5ff79-368">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="5ff79-369">Número da conta bancária (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-369">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="5ff79-370">Código SWIFT (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-370">SWIFT code (required)</span></span>          | <span data-ttu-id="5ff79-371">Campo **ID do banco** usado no processamento da folha de pagamento no México.</span><span class="sxs-lookup"><span data-stu-id="5ff79-371">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="5ff79-372">Número da agência (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-372">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="5ff79-373">Tipo de conta bancária (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-373">Bank account type (required)</span></span>   | <span data-ttu-id="5ff79-374">Campo **Tipo de conta** usado no processamento da folha de pagamento no México.</span><span class="sxs-lookup"><span data-stu-id="5ff79-374">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="5ff79-375">Os valores com suporte incluem **Movimento** e **Folha de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="5ff79-375">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="5ff79-376">Os funcionários que optarem por serem pagos por meio de transferências bancárias deverão fornecer um link para uma conta de pendência em uma entidade legal que tenha seu endereço principal no México e esteja associada a uma conta bancária válida de um banco mexicano.</span><span class="sxs-lookup"><span data-stu-id="5ff79-376">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="5ff79-377">Todas as outras contas que não são de pendência são ignoradas.</span><span class="sxs-lookup"><span data-stu-id="5ff79-377">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="5ff79-378">Informações de endereço</span><span class="sxs-lookup"><span data-stu-id="5ff79-378">Address information</span></span>

<span data-ttu-id="5ff79-379">Todos os funcionários devem ter um local principal.</span><span class="sxs-lookup"><span data-stu-id="5ff79-379">Every employee must have one primary location.</span></span> <span data-ttu-id="5ff79-380">No Dayforce, esse local é usado para determinar a residência principal do funcionário para fins fiscais.</span><span class="sxs-lookup"><span data-stu-id="5ff79-380">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="5ff79-381">Principal (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-381">Primary (required)</span></span>
- <span data-ttu-id="5ff79-382">País/região (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-382">Country/region (required)</span></span>
- <span data-ttu-id="5ff79-383">CEP (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-383">Zip/postal code (required)</span></span>
- <span data-ttu-id="5ff79-384">Rua (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="5ff79-384">Street (required)</span></span>
- <span data-ttu-id="5ff79-385">Número da rua (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-385">Street Number (required)</span></span>
- <span data-ttu-id="5ff79-386">Complemento do edifício</span><span class="sxs-lookup"><span data-stu-id="5ff79-386">Building Complement</span></span>
- <span data-ttu-id="5ff79-387">Cidade (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="5ff79-387">City (required)</span></span>
- <span data-ttu-id="5ff79-388">Estado (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-388">State (required)</span></span>
- <span data-ttu-id="5ff79-389">Município (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-389">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="5ff79-390">Configurar seus dados para gerar folha de pagamento nos Estados Unidos e no Canadá</span><span class="sxs-lookup"><span data-stu-id="5ff79-390">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="5ff79-391">Se você está gerando pagamento para funcionários nos Estados Unidos e no Canadá, os seguintes elementos devem ser configurados:</span><span class="sxs-lookup"><span data-stu-id="5ff79-391">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="5ff79-392">Departamentos são necessários em posições.</span><span class="sxs-lookup"><span data-stu-id="5ff79-392">Departments are required on positions.</span></span>
- <span data-ttu-id="5ff79-393">Os centros de custo devem ser definidos como dimensões financeiras e ser o primeiro elemento na sequência de dimensão financeira padrão.</span><span class="sxs-lookup"><span data-stu-id="5ff79-393">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

> [!NOTE] 
> <span data-ttu-id="5ff79-394">Você pode configurar o Human Resources para exigir que Posições especifique um Departamento.</span><span class="sxs-lookup"><span data-stu-id="5ff79-394">You can configure Human Resources to require that Positions specify a Department.</span></span> <span data-ttu-id="5ff79-395">Para isso, acesse **Posições Compartilhadas de Recursos Humanos > Posições > Exigir departamentos nas posições**.</span><span class="sxs-lookup"><span data-stu-id="5ff79-395">To do this, go to **Human Resources Shared Positions > Positions > Require departments on positions**.</span></span> <span data-ttu-id="5ff79-396">Recomendamos que esta configuração seja imposta para a integração.</span><span class="sxs-lookup"><span data-stu-id="5ff79-396">We recommend that this setting be enforced for the integration.</span></span>

### <a name="job-types"></a><span data-ttu-id="5ff79-397">Tipos de trabalho</span><span class="sxs-lookup"><span data-stu-id="5ff79-397">Job types</span></span>

<span data-ttu-id="5ff79-398">Os tipos de trabalho são usados para agrupar trabalhos semelhantes em categorias.</span><span class="sxs-lookup"><span data-stu-id="5ff79-398">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="5ff79-399">Os tipos de trabalho são necessários para processar a folha de pagamento nos Estados Unidos e no Canadá.</span><span class="sxs-lookup"><span data-stu-id="5ff79-399">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="5ff79-400">Os exemplos de tipos de trabalho incluem horário integral e meio período ou salário e pagamento por hora.</span><span class="sxs-lookup"><span data-stu-id="5ff79-400">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="5ff79-401">Os tipos de trabalho são mapeados para o Dayforce como tipos de pagamento que indicam se um funcionário é pago por hora ou assalariado.</span><span class="sxs-lookup"><span data-stu-id="5ff79-401">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="5ff79-402">Os seguintes tipos de trabalho e descrições são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="5ff79-402">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="5ff79-403">Tipo de trabalho</span><span class="sxs-lookup"><span data-stu-id="5ff79-403">Job type</span></span>   | <span data-ttu-id="5ff79-404">descrição</span><span class="sxs-lookup"><span data-stu-id="5ff79-404">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="5ff79-405">Por hora</span><span class="sxs-lookup"><span data-stu-id="5ff79-405">Hourly</span></span>     | <span data-ttu-id="5ff79-406">Por hora</span><span class="sxs-lookup"><span data-stu-id="5ff79-406">Hourly</span></span>      |
| <span data-ttu-id="5ff79-407">Assalariado</span><span class="sxs-lookup"><span data-stu-id="5ff79-407">Salaried</span></span>   | <span data-ttu-id="5ff79-408">Assalariado</span><span class="sxs-lookup"><span data-stu-id="5ff79-408">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="5ff79-409">Tipos de posição</span><span class="sxs-lookup"><span data-stu-id="5ff79-409">Position types</span></span> 

<span data-ttu-id="5ff79-410">Você usa os tipos de posição para descrever se a posição é de tempo integral, meio período ou de outra natureza.</span><span class="sxs-lookup"><span data-stu-id="5ff79-410">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="5ff79-411">Os tipos de posição são mapeados para o Dayforce como classes de pagamento que indicam se um funcionário é de tempo integral ou meio período.</span><span class="sxs-lookup"><span data-stu-id="5ff79-411">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="5ff79-412">Os seguintes tipos de posição e descrições são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="5ff79-412">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="5ff79-413">Tipo de posição</span><span class="sxs-lookup"><span data-stu-id="5ff79-413">Position type</span></span>   | <span data-ttu-id="5ff79-414">descrição</span><span class="sxs-lookup"><span data-stu-id="5ff79-414">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="5ff79-415">Horário integral</span><span class="sxs-lookup"><span data-stu-id="5ff79-415">Full-time</span></span>       | <span data-ttu-id="5ff79-416">Funcionário de tempo integral</span><span class="sxs-lookup"><span data-stu-id="5ff79-416">Full time employee</span></span> |
| <span data-ttu-id="5ff79-417">Meio período</span><span class="sxs-lookup"><span data-stu-id="5ff79-417">Part-time</span></span>       | <span data-ttu-id="5ff79-418">Funcionário de meio período</span><span class="sxs-lookup"><span data-stu-id="5ff79-418">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="5ff79-419">Códigos de motivos</span><span class="sxs-lookup"><span data-stu-id="5ff79-419">Reason codes</span></span>

<span data-ttu-id="5ff79-420">Códigos de motivo fornecem informações sobre o status de um funcionário.</span><span class="sxs-lookup"><span data-stu-id="5ff79-420">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="5ff79-421">Os códigos de motivo são mapeados para o Dayforce como motivos de status que indicam o motivo das alterações na posição de um funcionário ou no status de um emprego.</span><span class="sxs-lookup"><span data-stu-id="5ff79-421">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="5ff79-422">Os seguintes códigos de motivo e descrições são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="5ff79-422">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="5ff79-423">Código de motivo</span><span class="sxs-lookup"><span data-stu-id="5ff79-423">Reason code</span></span>    | <span data-ttu-id="5ff79-424">descrição</span><span class="sxs-lookup"><span data-stu-id="5ff79-424">Description</span></span>      | <span data-ttu-id="5ff79-425">Cenários aplicáveis</span><span class="sxs-lookup"><span data-stu-id="5ff79-425">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="5ff79-426">DEMISSÃO</span><span class="sxs-lookup"><span data-stu-id="5ff79-426">RESIGNATION</span></span>    | <span data-ttu-id="5ff79-427">Demissão</span><span class="sxs-lookup"><span data-stu-id="5ff79-427">Resignation</span></span>      | <span data-ttu-id="5ff79-428">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="5ff79-428">Terminate worker</span></span>     |
| <span data-ttu-id="5ff79-429">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="5ff79-429">TERMINATION</span></span>    | <span data-ttu-id="5ff79-430">Finalização</span><span class="sxs-lookup"><span data-stu-id="5ff79-430">Termination</span></span>      | <span data-ttu-id="5ff79-431">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="5ff79-431">Terminate worker</span></span>     |
| <span data-ttu-id="5ff79-432">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="5ff79-432">RETIREMENT</span></span>     | <span data-ttu-id="5ff79-433">Aposentadoria</span><span class="sxs-lookup"><span data-stu-id="5ff79-433">Retirement</span></span>       | <span data-ttu-id="5ff79-434">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="5ff79-434">Terminate worker</span></span>     |
| <span data-ttu-id="5ff79-435">OTHER</span><span class="sxs-lookup"><span data-stu-id="5ff79-435">OTHER</span></span>          | <span data-ttu-id="5ff79-436">Outros motivos</span><span class="sxs-lookup"><span data-stu-id="5ff79-436">Other Reasons</span></span>    | <span data-ttu-id="5ff79-437">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="5ff79-437">Terminate worker</span></span>     |
| <span data-ttu-id="5ff79-438">DEATH</span><span class="sxs-lookup"><span data-stu-id="5ff79-438">DEATH</span></span>          | <span data-ttu-id="5ff79-439">Morte</span><span class="sxs-lookup"><span data-stu-id="5ff79-439">Death</span></span>            | <span data-ttu-id="5ff79-440">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="5ff79-440">Terminate worker</span></span>     |
| <span data-ttu-id="5ff79-441">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="5ff79-441">LEAVEOFABSENCE</span></span> | <span data-ttu-id="5ff79-442">Licença</span><span class="sxs-lookup"><span data-stu-id="5ff79-442">Leave of Absence</span></span> | <span data-ttu-id="5ff79-443">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="5ff79-443">Terminate worker</span></span>     |
| <span data-ttu-id="5ff79-444">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="5ff79-444">CONTRACTEND</span></span>    | <span data-ttu-id="5ff79-445">Fim do contrato</span><span class="sxs-lookup"><span data-stu-id="5ff79-445">End of Contract</span></span>  | <span data-ttu-id="5ff79-446">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="5ff79-446">Terminate worker</span></span>     |
| <span data-ttu-id="5ff79-447">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="5ff79-447">SALARYCHANGE</span></span>   | <span data-ttu-id="5ff79-448">Alteração de salário</span><span class="sxs-lookup"><span data-stu-id="5ff79-448">Change of Salary</span></span> | <span data-ttu-id="5ff79-449">Remuneração</span><span class="sxs-lookup"><span data-stu-id="5ff79-449">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="5ff79-450">Estado civil</span><span class="sxs-lookup"><span data-stu-id="5ff79-450">Marital status</span></span>

<span data-ttu-id="5ff79-451">Os valores do estado civil são mapeados para o Dayforce e convertidos, conforme apropriado, nos valores aceitos após a integração.</span><span class="sxs-lookup"><span data-stu-id="5ff79-451">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="5ff79-452">A tabela a seguir mostra como os valores do estado civil são mapeados para o Dayforce.</span><span class="sxs-lookup"><span data-stu-id="5ff79-452">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="5ff79-453">Recursos Humanos</span><span class="sxs-lookup"><span data-stu-id="5ff79-453">Human Resources</span></span>                 | <span data-ttu-id="5ff79-454">Dayforce</span><span class="sxs-lookup"><span data-stu-id="5ff79-454">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="5ff79-455">Casado(a)</span><span class="sxs-lookup"><span data-stu-id="5ff79-455">Married</span></span>                | <span data-ttu-id="5ff79-456">Casado(a)</span><span class="sxs-lookup"><span data-stu-id="5ff79-456">Married</span></span>              |
| <span data-ttu-id="5ff79-457">Único</span><span class="sxs-lookup"><span data-stu-id="5ff79-457">Single</span></span>                 | <span data-ttu-id="5ff79-458">Único</span><span class="sxs-lookup"><span data-stu-id="5ff79-458">Single</span></span>               |
| <span data-ttu-id="5ff79-459">Viúvo(a)</span><span class="sxs-lookup"><span data-stu-id="5ff79-459">Widowed</span></span>                | <span data-ttu-id="5ff79-460">Viúvo(a)</span><span class="sxs-lookup"><span data-stu-id="5ff79-460">Widowed</span></span>              |
| <span data-ttu-id="5ff79-461">Divorciado(a)</span><span class="sxs-lookup"><span data-stu-id="5ff79-461">Divorced</span></span>               | <span data-ttu-id="5ff79-462">Divorciado(a)</span><span class="sxs-lookup"><span data-stu-id="5ff79-462">Divorced</span></span>             |
| <span data-ttu-id="5ff79-463">Parceria Registrada</span><span class="sxs-lookup"><span data-stu-id="5ff79-463">Registered Partnership</span></span> | <span data-ttu-id="5ff79-464">Parceiro doméstico</span><span class="sxs-lookup"><span data-stu-id="5ff79-464">Domestic Partnership</span></span> |
| <span data-ttu-id="5ff79-465">Nenhum(a)</span><span class="sxs-lookup"><span data-stu-id="5ff79-465">None</span></span>                   | <span data-ttu-id="5ff79-466">Nenhum(a)</span><span class="sxs-lookup"><span data-stu-id="5ff79-466">None</span></span>                 |
| <span data-ttu-id="5ff79-467">Coabitando</span><span class="sxs-lookup"><span data-stu-id="5ff79-467">Cohabiting</span></span>             | <span data-ttu-id="5ff79-468">Coabitando</span><span class="sxs-lookup"><span data-stu-id="5ff79-468">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="5ff79-469">Sexo</span><span class="sxs-lookup"><span data-stu-id="5ff79-469">Gender</span></span>

<span data-ttu-id="5ff79-470">As designações de gênero são mapeadas para o Dayforce e convertidas, conforme apropriado, nos valores aceitos após a integração.</span><span class="sxs-lookup"><span data-stu-id="5ff79-470">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="5ff79-471">A tabela a seguir mostra como as designações de gênero são mapeadas para o Dayforce.</span><span class="sxs-lookup"><span data-stu-id="5ff79-471">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="5ff79-472">Recursos Humanos</span><span class="sxs-lookup"><span data-stu-id="5ff79-472">Human Resources</span></span>       | <span data-ttu-id="5ff79-473">Dayforce</span><span class="sxs-lookup"><span data-stu-id="5ff79-473">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="5ff79-474">Masculino</span><span class="sxs-lookup"><span data-stu-id="5ff79-474">Male</span></span>         | <span data-ttu-id="5ff79-475">Masculino</span><span class="sxs-lookup"><span data-stu-id="5ff79-475">Male</span></span>            |
| <span data-ttu-id="5ff79-476">Feminino</span><span class="sxs-lookup"><span data-stu-id="5ff79-476">Female</span></span>       | <span data-ttu-id="5ff79-477">Feminino</span><span class="sxs-lookup"><span data-stu-id="5ff79-477">Female</span></span>          |
| <span data-ttu-id="5ff79-478">Não específico</span><span class="sxs-lookup"><span data-stu-id="5ff79-478">Non-specific</span></span> | <span data-ttu-id="5ff79-479">*Sem suporte*</span><span class="sxs-lookup"><span data-stu-id="5ff79-479">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="5ff79-480">Códigos de ganhos</span><span class="sxs-lookup"><span data-stu-id="5ff79-480">Earning codes</span></span>

<span data-ttu-id="5ff79-481">Os códigos de ganhos identificam de forma exclusiva cada tipo de ganho que os trabalhadores recebem.</span><span class="sxs-lookup"><span data-stu-id="5ff79-481">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="5ff79-482">Os códigos abordam vários parâmetros relacionados a ganhos, como regras contábeis, leis tributárias, requisitos de relatório e capacidade de montante bruto.</span><span class="sxs-lookup"><span data-stu-id="5ff79-482">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="5ff79-483">Se uma frequência sem suporte for usada, a frequência **Cada pagamento** é usada por padrão para o cálculo.</span><span class="sxs-lookup"><span data-stu-id="5ff79-483">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="5ff79-484">Frequências com suporte</span><span class="sxs-lookup"><span data-stu-id="5ff79-484">Supported frequencies</span></span>

- <span data-ttu-id="5ff79-485">Todas</span><span class="sxs-lookup"><span data-stu-id="5ff79-485">All</span></span>
- <span data-ttu-id="5ff79-486">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="5ff79-486">EVERYPAY</span></span>
- <span data-ttu-id="5ff79-487">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="5ff79-487">EACHPAYPERIOD</span></span>
- <span data-ttu-id="5ff79-488">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="5ff79-488">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="5ff79-489">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="5ff79-489">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="5ff79-490">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="5ff79-490">1OFMTH</span></span>
- <span data-ttu-id="5ff79-491">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="5ff79-491">LASTOFMTH</span></span>
- <span data-ttu-id="5ff79-492">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="5ff79-492">2OFMTH</span></span>
- <span data-ttu-id="5ff79-493">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="5ff79-493">3OFMTH</span></span>
- <span data-ttu-id="5ff79-494">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="5ff79-494">4OFMTH</span></span>
- <span data-ttu-id="5ff79-495">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="5ff79-495">5OFMTH</span></span>
- <span data-ttu-id="5ff79-496">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="5ff79-496">1N2OFMTH</span></span>
- <span data-ttu-id="5ff79-497">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="5ff79-497">3N4OFMTH</span></span>
- <span data-ttu-id="5ff79-498">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="5ff79-498">1N3OFMTH</span></span>
- <span data-ttu-id="5ff79-499">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="5ff79-499">1N4OFMTH</span></span>
- <span data-ttu-id="5ff79-500">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="5ff79-500">2N3OFMTH</span></span>
- <span data-ttu-id="5ff79-501">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="5ff79-501">2N4OFMTH</span></span>
- <span data-ttu-id="5ff79-502">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="5ff79-502">1N2N3OFMTH</span></span>
- <span data-ttu-id="5ff79-503">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="5ff79-503">1N2N4OFMTH</span></span>
- <span data-ttu-id="5ff79-504">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="5ff79-504">1N3N4OFMTH</span></span>
- <span data-ttu-id="5ff79-505">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="5ff79-505">2N3N4OFMTH</span></span>
- <span data-ttu-id="5ff79-506">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="5ff79-506">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="5ff79-507">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="5ff79-507">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="5ff79-508">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="5ff79-508">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="5ff79-509">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="5ff79-509">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="5ff79-510">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="5ff79-510">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="5ff79-511">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="5ff79-511">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="5ff79-512">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="5ff79-512">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="5ff79-513">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="5ff79-513">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="5ff79-514">Endereços</span><span class="sxs-lookup"><span data-stu-id="5ff79-514">Addresses</span></span>

<span data-ttu-id="5ff79-515">A identificação de códigos específicos de país ou região, estado e município (municipalidade) exige formatos específicos que o Dayforce e os provedores no país/na região possam reconhecer.</span><span class="sxs-lookup"><span data-stu-id="5ff79-515">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="5ff79-516">Embora o formato das cidades seja flexível, todas as cidades devem estar associadas a um estado.</span><span class="sxs-lookup"><span data-stu-id="5ff79-516">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="5ff79-517">Recursos Humanos</span><span class="sxs-lookup"><span data-stu-id="5ff79-517">Human Resources</span></span>          | <span data-ttu-id="5ff79-518">Dayforce</span><span class="sxs-lookup"><span data-stu-id="5ff79-518">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="5ff79-519">País/Região</span><span class="sxs-lookup"><span data-stu-id="5ff79-519">Country/Region</span></span>  | <span data-ttu-id="5ff79-520">Código do País</span><span class="sxs-lookup"><span data-stu-id="5ff79-520">Country Code</span></span>          |
| <span data-ttu-id="5ff79-521">CEP</span><span class="sxs-lookup"><span data-stu-id="5ff79-521">Zip/Postal Code</span></span> | <span data-ttu-id="5ff79-522">CEP</span><span class="sxs-lookup"><span data-stu-id="5ff79-522">Postal Code</span></span>           |
| <span data-ttu-id="5ff79-523">Estadual</span><span class="sxs-lookup"><span data-stu-id="5ff79-523">State</span></span>           | <span data-ttu-id="5ff79-524">Código de estado</span><span class="sxs-lookup"><span data-stu-id="5ff79-524">State Code</span></span>            |
| <span data-ttu-id="5ff79-525">Cidade</span><span class="sxs-lookup"><span data-stu-id="5ff79-525">City</span></span>            | <span data-ttu-id="5ff79-526">Cidade</span><span class="sxs-lookup"><span data-stu-id="5ff79-526">City</span></span>                  |
| <span data-ttu-id="5ff79-527">Região</span><span class="sxs-lookup"><span data-stu-id="5ff79-527">County</span></span>          | <span data-ttu-id="5ff79-528">Município (municipalidade)</span><span class="sxs-lookup"><span data-stu-id="5ff79-528">County (Municipality)</span></span> |
| <span data-ttu-id="5ff79-529">Rua</span><span class="sxs-lookup"><span data-stu-id="5ff79-529">Street</span></span>          | <span data-ttu-id="5ff79-530">Linha de endereço 1</span><span class="sxs-lookup"><span data-stu-id="5ff79-530">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="5ff79-531">Regiões fiscais</span><span class="sxs-lookup"><span data-stu-id="5ff79-531">Tax regions</span></span>

<span data-ttu-id="5ff79-532">Regiões fiscais são usadas para determinar os impostos apropriados a serem aplicados durante a geração da folha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="5ff79-532">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="5ff79-533">As regiões fiscais são mapeadas para o Dayforce como endereços de localização.</span><span class="sxs-lookup"><span data-stu-id="5ff79-533">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="5ff79-534">A região fiscal padrão deve estar associada à posição ativa do trabalhador.</span><span class="sxs-lookup"><span data-stu-id="5ff79-534">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="5ff79-535">Região fiscal (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="5ff79-535">Tax region (required)</span></span>
- <span data-ttu-id="5ff79-536">País/região (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-536">Country/Region (required)</span></span>
- <span data-ttu-id="5ff79-537">Estado (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5ff79-537">State (required)</span></span>
- <span data-ttu-id="5ff79-538">Região</span><span class="sxs-lookup"><span data-stu-id="5ff79-538">County</span></span> 
- <span data-ttu-id="5ff79-539">Cidade (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="5ff79-539">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="5ff79-540">Configurar seus dados para gerar folha de pagamento no México</span><span class="sxs-lookup"><span data-stu-id="5ff79-540">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="5ff79-541">Se você está gerando pagamento para funcionários no México, os seguintes elementos devem ser configurados:</span><span class="sxs-lookup"><span data-stu-id="5ff79-541">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="5ff79-542">Departamentos são necessários em posições.</span><span class="sxs-lookup"><span data-stu-id="5ff79-542">Departments are required on positions.</span></span>
- <span data-ttu-id="5ff79-543">Os centros de custo devem ser definidos como dimensões financeiras e ser o primeiro elemento na sequência de dimensão financeira padrão.</span><span class="sxs-lookup"><span data-stu-id="5ff79-543">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="5ff79-544">Tipos de trabalho</span><span class="sxs-lookup"><span data-stu-id="5ff79-544">Job types</span></span>

<span data-ttu-id="5ff79-545">Os tipos de trabalho são usados para agrupar trabalhos semelhantes em categorias.</span><span class="sxs-lookup"><span data-stu-id="5ff79-545">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="5ff79-546">Tipos de trabalho são necessários para processar a folha de pagamento no México.</span><span class="sxs-lookup"><span data-stu-id="5ff79-546">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="5ff79-547">Os exemplos de tipos de trabalho incluem horário integral e meio período ou salário e pagamento por hora.</span><span class="sxs-lookup"><span data-stu-id="5ff79-547">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="5ff79-548">Os tipos de trabalho são mapeados para o Dayforce como tipos de pagamento que indicam se um funcionário é pago por hora ou assalariado.</span><span class="sxs-lookup"><span data-stu-id="5ff79-548">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="5ff79-549">Os seguintes tipos de trabalho e descrições são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="5ff79-549">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="5ff79-550">Tipo de trabalho</span><span class="sxs-lookup"><span data-stu-id="5ff79-550">Job type</span></span>   | <span data-ttu-id="5ff79-551">descrição</span><span class="sxs-lookup"><span data-stu-id="5ff79-551">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="5ff79-552">Por hora</span><span class="sxs-lookup"><span data-stu-id="5ff79-552">Hourly</span></span>     | <span data-ttu-id="5ff79-553">MX por hora</span><span class="sxs-lookup"><span data-stu-id="5ff79-553">MX Hourly</span></span>   |
| <span data-ttu-id="5ff79-554">Assalariado</span><span class="sxs-lookup"><span data-stu-id="5ff79-554">Salaried</span></span>   | <span data-ttu-id="5ff79-555">MX assalariado</span><span class="sxs-lookup"><span data-stu-id="5ff79-555">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="5ff79-556">Tipos de posição</span><span class="sxs-lookup"><span data-stu-id="5ff79-556">Position types</span></span> 

<span data-ttu-id="5ff79-557">Você usa os tipos de posição para descrever se a posição é de tempo integral, meio período ou de outra natureza.</span><span class="sxs-lookup"><span data-stu-id="5ff79-557">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="5ff79-558">Os tipos de posição são mapeados para o Dayforce como classes de pagamento que indicam se um funcionário é de tempo integral ou meio período.</span><span class="sxs-lookup"><span data-stu-id="5ff79-558">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="5ff79-559">Os seguintes tipos de posição e descrições são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="5ff79-559">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="5ff79-560">Tipo de posição</span><span class="sxs-lookup"><span data-stu-id="5ff79-560">Position type</span></span>   | <span data-ttu-id="5ff79-561">descrição</span><span class="sxs-lookup"><span data-stu-id="5ff79-561">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="5ff79-562">Horário integral</span><span class="sxs-lookup"><span data-stu-id="5ff79-562">Full-time</span></span>       | <span data-ttu-id="5ff79-563">Funcionário de tempo integral</span><span class="sxs-lookup"><span data-stu-id="5ff79-563">Full time employee</span></span> |
| <span data-ttu-id="5ff79-564">Meio período</span><span class="sxs-lookup"><span data-stu-id="5ff79-564">Part-time</span></span>       | <span data-ttu-id="5ff79-565">Funcionário de meio período</span><span class="sxs-lookup"><span data-stu-id="5ff79-565">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="5ff79-566">Códigos de motivos</span><span class="sxs-lookup"><span data-stu-id="5ff79-566">Reason codes</span></span>

<span data-ttu-id="5ff79-567">Códigos de motivo fornecem informações sobre o status de um funcionário.</span><span class="sxs-lookup"><span data-stu-id="5ff79-567">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="5ff79-568">Os códigos de motivo são mapeados para o Dayforce como motivos de status que indicam o motivo das alterações na posição de um funcionário ou no status de um emprego.</span><span class="sxs-lookup"><span data-stu-id="5ff79-568">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="5ff79-569">Os seguintes códigos de motivo e descrições são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="5ff79-569">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="5ff79-570">Código de motivo</span><span class="sxs-lookup"><span data-stu-id="5ff79-570">Reason code</span></span>            | <span data-ttu-id="5ff79-571">descrição</span><span class="sxs-lookup"><span data-stu-id="5ff79-571">Description</span></span>                    | <span data-ttu-id="5ff79-572">Cenários aplicáveis</span><span class="sxs-lookup"><span data-stu-id="5ff79-572">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="5ff79-573">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="5ff79-573">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="5ff79-574">Partida antes da primeira folha de pagamento</span><span class="sxs-lookup"><span data-stu-id="5ff79-574">Departure before first payroll</span></span> | <span data-ttu-id="5ff79-575">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="5ff79-575">Terminate worker</span></span>     |
| <span data-ttu-id="5ff79-576">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="5ff79-576">RESIGNATION</span></span>            | <span data-ttu-id="5ff79-577">Demissão</span><span class="sxs-lookup"><span data-stu-id="5ff79-577">Resignation</span></span>                    | <span data-ttu-id="5ff79-578">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="5ff79-578">Terminate worker</span></span>     |
| <span data-ttu-id="5ff79-579">PENSION</span><span class="sxs-lookup"><span data-stu-id="5ff79-579">PENSION</span></span>                | <span data-ttu-id="5ff79-580">Aposentadoria</span><span class="sxs-lookup"><span data-stu-id="5ff79-580">Pension</span></span>                        | <span data-ttu-id="5ff79-581">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="5ff79-581">Terminate worker</span></span>     |
| <span data-ttu-id="5ff79-582">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="5ff79-582">TERMINATION</span></span>            | <span data-ttu-id="5ff79-583">Finalização</span><span class="sxs-lookup"><span data-stu-id="5ff79-583">Termination</span></span>                    | <span data-ttu-id="5ff79-584">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="5ff79-584">Terminate worker</span></span>     |
| <span data-ttu-id="5ff79-585">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="5ff79-585">RETIREMENT</span></span>             | <span data-ttu-id="5ff79-586">Aposentadoria</span><span class="sxs-lookup"><span data-stu-id="5ff79-586">Retirement</span></span>                     | <span data-ttu-id="5ff79-587">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="5ff79-587">Terminate worker</span></span>     |
| <span data-ttu-id="5ff79-588">ABSENTEE</span><span class="sxs-lookup"><span data-stu-id="5ff79-588">ABSENTEE</span></span>               | <span data-ttu-id="5ff79-589">Absentista</span><span class="sxs-lookup"><span data-stu-id="5ff79-589">Absentee</span></span>                       | <span data-ttu-id="5ff79-590">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="5ff79-590">Terminate worker</span></span>     |
| <span data-ttu-id="5ff79-591">OTHER</span><span class="sxs-lookup"><span data-stu-id="5ff79-591">OTHER</span></span>                  | <span data-ttu-id="5ff79-592">Outros motivos</span><span class="sxs-lookup"><span data-stu-id="5ff79-592">Other Reasons</span></span>                  | <span data-ttu-id="5ff79-593">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="5ff79-593">Terminate worker</span></span>     |
| <span data-ttu-id="5ff79-594">CLOSURE</span><span class="sxs-lookup"><span data-stu-id="5ff79-594">CLOSURE</span></span>                | <span data-ttu-id="5ff79-595">Fechamento da empresa</span><span class="sxs-lookup"><span data-stu-id="5ff79-595">Business Closure</span></span>               | <span data-ttu-id="5ff79-596">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="5ff79-596">Terminate worker</span></span>     |
| <span data-ttu-id="5ff79-597">DEATH</span><span class="sxs-lookup"><span data-stu-id="5ff79-597">DEATH</span></span>                  | <span data-ttu-id="5ff79-598">Morte</span><span class="sxs-lookup"><span data-stu-id="5ff79-598">Death</span></span>                          | <span data-ttu-id="5ff79-599">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="5ff79-599">Terminate worker</span></span>     |
| <span data-ttu-id="5ff79-600">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="5ff79-600">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="5ff79-601">Licença</span><span class="sxs-lookup"><span data-stu-id="5ff79-601">Leave of Absence</span></span>               | <span data-ttu-id="5ff79-602">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="5ff79-602">Terminate worker</span></span>     |
| <span data-ttu-id="5ff79-603">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="5ff79-603">CONTRACTEND</span></span>            | <span data-ttu-id="5ff79-604">Fim do contrato</span><span class="sxs-lookup"><span data-stu-id="5ff79-604">End of Contract</span></span>                | <span data-ttu-id="5ff79-605">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="5ff79-605">Terminate worker</span></span>     |
| <span data-ttu-id="5ff79-606">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="5ff79-606">SALARYCHANGE</span></span>           | <span data-ttu-id="5ff79-607">Alteração de salário</span><span class="sxs-lookup"><span data-stu-id="5ff79-607">Change of Salary</span></span>               | <span data-ttu-id="5ff79-608">Remuneração</span><span class="sxs-lookup"><span data-stu-id="5ff79-608">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="5ff79-609">Contrato de trabalho</span><span class="sxs-lookup"><span data-stu-id="5ff79-609">Terms of employment</span></span>

<span data-ttu-id="5ff79-610">Termos de emprego são usados para criar categorias de termos de emprego.</span><span class="sxs-lookup"><span data-stu-id="5ff79-610">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="5ff79-611">Os termos são mapeados para o Dayforce como valores de indicador de emprego.</span><span class="sxs-lookup"><span data-stu-id="5ff79-611">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="5ff79-612">Os termos de emprego e as descrições a seguir são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="5ff79-612">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="5ff79-613">Contrato de trabalho</span><span class="sxs-lookup"><span data-stu-id="5ff79-613">Terms of employment</span></span>   | <span data-ttu-id="5ff79-614">descrição</span><span class="sxs-lookup"><span data-stu-id="5ff79-614">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="5ff79-615">Normal</span><span class="sxs-lookup"><span data-stu-id="5ff79-615">Regular</span></span>               | <span data-ttu-id="5ff79-616">Normal</span><span class="sxs-lookup"><span data-stu-id="5ff79-616">Regular</span></span>     |
| <span data-ttu-id="5ff79-617">Direto</span><span class="sxs-lookup"><span data-stu-id="5ff79-617">Direct</span></span>                | <span data-ttu-id="5ff79-618">Direto</span><span class="sxs-lookup"><span data-stu-id="5ff79-618">Direct</span></span>      |
| <span data-ttu-id="5ff79-619">Estágio</span><span class="sxs-lookup"><span data-stu-id="5ff79-619">Internship</span></span>            | <span data-ttu-id="5ff79-620">Estágio</span><span class="sxs-lookup"><span data-stu-id="5ff79-620">Internship</span></span>  |
| <span data-ttu-id="5ff79-621">Permanente</span><span class="sxs-lookup"><span data-stu-id="5ff79-621">Permanent</span></span>             | <span data-ttu-id="5ff79-622">Permanente</span><span class="sxs-lookup"><span data-stu-id="5ff79-622">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="5ff79-623">Estado civil</span><span class="sxs-lookup"><span data-stu-id="5ff79-623">Marital status</span></span>

<span data-ttu-id="5ff79-624">Os valores do estado civil são mapeados para o Dayforce e convertidos, conforme apropriado, nos valores aceitos após a integração.</span><span class="sxs-lookup"><span data-stu-id="5ff79-624">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="5ff79-625">A tabela a seguir mostra como os valores do estado civil são mapeados para o Dayforce.</span><span class="sxs-lookup"><span data-stu-id="5ff79-625">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="5ff79-626">Recursos Humanos</span><span class="sxs-lookup"><span data-stu-id="5ff79-626">Human Resources</span></span>                 | <span data-ttu-id="5ff79-627">Dayforce</span><span class="sxs-lookup"><span data-stu-id="5ff79-627">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="5ff79-628">Casado(a)</span><span class="sxs-lookup"><span data-stu-id="5ff79-628">Married</span></span>                | <span data-ttu-id="5ff79-629">Casado(a)</span><span class="sxs-lookup"><span data-stu-id="5ff79-629">Married</span></span>                   |
| <span data-ttu-id="5ff79-630">Único</span><span class="sxs-lookup"><span data-stu-id="5ff79-630">Single</span></span>                 | <span data-ttu-id="5ff79-631">Único</span><span class="sxs-lookup"><span data-stu-id="5ff79-631">Single</span></span>                    |
| <span data-ttu-id="5ff79-632">Viúvo(a)</span><span class="sxs-lookup"><span data-stu-id="5ff79-632">Widowed</span></span>                | <span data-ttu-id="5ff79-633">Viúvo(a)</span><span class="sxs-lookup"><span data-stu-id="5ff79-633">Widowed</span></span>                   |
| <span data-ttu-id="5ff79-634">Divorciado(a)</span><span class="sxs-lookup"><span data-stu-id="5ff79-634">Divorced</span></span>               | <span data-ttu-id="5ff79-635">Divorciado(a)</span><span class="sxs-lookup"><span data-stu-id="5ff79-635">Divorced</span></span>                  |
| <span data-ttu-id="5ff79-636">Parceria Registrada</span><span class="sxs-lookup"><span data-stu-id="5ff79-636">Registered Partnership</span></span> | <span data-ttu-id="5ff79-637">Parceiro doméstico</span><span class="sxs-lookup"><span data-stu-id="5ff79-637">Domestic Partnership</span></span>      |
| <span data-ttu-id="5ff79-638">Nenhum(a)</span><span class="sxs-lookup"><span data-stu-id="5ff79-638">None</span></span>                   | <span data-ttu-id="5ff79-639">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="5ff79-639">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="5ff79-640">Coabitando</span><span class="sxs-lookup"><span data-stu-id="5ff79-640">Cohabiting</span></span>             | <span data-ttu-id="5ff79-641">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="5ff79-641">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="5ff79-642">Sexo</span><span class="sxs-lookup"><span data-stu-id="5ff79-642">Gender</span></span>

<span data-ttu-id="5ff79-643">As designações de gênero são mapeadas para o Dayforce e convertidas, conforme apropriado, nos valores aceitos após a integração.</span><span class="sxs-lookup"><span data-stu-id="5ff79-643">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="5ff79-644">A tabela a seguir mostra como as designações de gênero são mapeadas para o Dayforce.</span><span class="sxs-lookup"><span data-stu-id="5ff79-644">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="5ff79-645">Recursos Humanos</span><span class="sxs-lookup"><span data-stu-id="5ff79-645">Human Resources</span></span>       | <span data-ttu-id="5ff79-646">Dayforce</span><span class="sxs-lookup"><span data-stu-id="5ff79-646">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="5ff79-647">Masculino</span><span class="sxs-lookup"><span data-stu-id="5ff79-647">Male</span></span>         | <span data-ttu-id="5ff79-648">Masculino</span><span class="sxs-lookup"><span data-stu-id="5ff79-648">Male</span></span>                      |
| <span data-ttu-id="5ff79-649">Feminino</span><span class="sxs-lookup"><span data-stu-id="5ff79-649">Female</span></span>       | <span data-ttu-id="5ff79-650">Feminino</span><span class="sxs-lookup"><span data-stu-id="5ff79-650">Female</span></span>                    |
| <span data-ttu-id="5ff79-651">Não específico</span><span class="sxs-lookup"><span data-stu-id="5ff79-651">Non-specific</span></span> | <span data-ttu-id="5ff79-652">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="5ff79-652">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="5ff79-653">Forma de pagamento</span><span class="sxs-lookup"><span data-stu-id="5ff79-653">Payment method</span></span>

<span data-ttu-id="5ff79-654">Os métodos de pagamento dão ao funcionário e à empresa uma maneira de descrever como os funcionários serão pagos.</span><span class="sxs-lookup"><span data-stu-id="5ff79-654">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="5ff79-655">Os métodos de pagamento são mapeados para o Dayforce e convertidos, conforme apropriado, nos valores aceitos após a integração.</span><span class="sxs-lookup"><span data-stu-id="5ff79-655">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="5ff79-656">A tabela a seguir mostra como os métodos de pagamento são mapeados para o Dayforce.</span><span class="sxs-lookup"><span data-stu-id="5ff79-656">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="5ff79-657">Recursos Humanos</span><span class="sxs-lookup"><span data-stu-id="5ff79-657">Human Resources</span></span>             | <span data-ttu-id="5ff79-658">Dayforce</span><span class="sxs-lookup"><span data-stu-id="5ff79-658">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="5ff79-659">Pagamento à vista</span><span class="sxs-lookup"><span data-stu-id="5ff79-659">Cash</span></span>               | <span data-ttu-id="5ff79-660">Pagamento à vista</span><span class="sxs-lookup"><span data-stu-id="5ff79-660">Cash</span></span>                      |
| <span data-ttu-id="5ff79-661">Pagamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="5ff79-661">Electronic Payment</span></span> | <span data-ttu-id="5ff79-662">Transferir</span><span class="sxs-lookup"><span data-stu-id="5ff79-662">Transfer</span></span>                  |
| <span data-ttu-id="5ff79-663">Marcar</span><span class="sxs-lookup"><span data-stu-id="5ff79-663">Check</span></span>              | <span data-ttu-id="5ff79-664">Cheque</span><span class="sxs-lookup"><span data-stu-id="5ff79-664">Cheque</span></span>                    |
| <span data-ttu-id="5ff79-665">Boleto bancário</span><span class="sxs-lookup"><span data-stu-id="5ff79-665">Bank Draft</span></span>         | <span data-ttu-id="5ff79-666">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="5ff79-666">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="5ff79-667">Outros</span><span class="sxs-lookup"><span data-stu-id="5ff79-667">Other</span></span>              | <span data-ttu-id="5ff79-668">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="5ff79-668">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="5ff79-669">Tipo de conta bancária</span><span class="sxs-lookup"><span data-stu-id="5ff79-669">Bank account type</span></span>

<span data-ttu-id="5ff79-670">Os tipos de conta bancária são usados para pagamentos eletrônicos aos funcionários.</span><span class="sxs-lookup"><span data-stu-id="5ff79-670">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="5ff79-671">Os tipos de conta bancária são mapeados para o Dayforce como informações da conta de transferência.</span><span class="sxs-lookup"><span data-stu-id="5ff79-671">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="5ff79-672">Os tipos de conta bancária são convertidos, conforme apropriado, nos valores aceitos após a integração.</span><span class="sxs-lookup"><span data-stu-id="5ff79-672">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="5ff79-673">Recursos Humanos</span><span class="sxs-lookup"><span data-stu-id="5ff79-673">Human Resources</span></span>            | <span data-ttu-id="5ff79-674">Dayforce</span><span class="sxs-lookup"><span data-stu-id="5ff79-674">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="5ff79-675">Conta corrente</span><span class="sxs-lookup"><span data-stu-id="5ff79-675">Checking Account</span></span>  | <span data-ttu-id="5ff79-676">CheckingAccount</span><span class="sxs-lookup"><span data-stu-id="5ff79-676">CheckingAccount</span></span>           |
| <span data-ttu-id="5ff79-677">Conta-salário</span><span class="sxs-lookup"><span data-stu-id="5ff79-677">Payroll Account</span></span>   | <span data-ttu-id="5ff79-678">PayrollAccount</span><span class="sxs-lookup"><span data-stu-id="5ff79-678">PayrollAccount</span></span>            |
| <span data-ttu-id="5ff79-679">Conta de poupança</span><span class="sxs-lookup"><span data-stu-id="5ff79-679">Savings Account</span></span>   | <span data-ttu-id="5ff79-680">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="5ff79-680">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="5ff79-681">Conta BankGirot</span><span class="sxs-lookup"><span data-stu-id="5ff79-681">BankGirot account</span></span> | <span data-ttu-id="5ff79-682">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="5ff79-682">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="5ff79-683">Conta PlusGirot</span><span class="sxs-lookup"><span data-stu-id="5ff79-683">PlusGirot account</span></span> | <span data-ttu-id="5ff79-684">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="5ff79-684">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="5ff79-685">Códigos de ganhos</span><span class="sxs-lookup"><span data-stu-id="5ff79-685">Earning codes</span></span>

<span data-ttu-id="5ff79-686">Os códigos de ganhos identificam de forma exclusiva cada tipo de ganho que os trabalhadores recebem.</span><span class="sxs-lookup"><span data-stu-id="5ff79-686">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="5ff79-687">Os códigos abordam vários parâmetros relacionados a ganhos, como regras contábeis, leis tributárias, requisitos de relatório e capacidade de montante bruto.</span><span class="sxs-lookup"><span data-stu-id="5ff79-687">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="5ff79-688">Se uma frequência sem suporte for usada, a frequência **Cada pagamento** é usada por padrão para o cálculo.</span><span class="sxs-lookup"><span data-stu-id="5ff79-688">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="5ff79-689">Frequências com suporte</span><span class="sxs-lookup"><span data-stu-id="5ff79-689">Supported frequencies</span></span>

- <span data-ttu-id="5ff79-690">Todas</span><span class="sxs-lookup"><span data-stu-id="5ff79-690">All</span></span>
- <span data-ttu-id="5ff79-691">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="5ff79-691">EVERYPAY</span></span>
- <span data-ttu-id="5ff79-692">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="5ff79-692">EACHPAYPERIOD</span></span>
- <span data-ttu-id="5ff79-693">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="5ff79-693">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="5ff79-694">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="5ff79-694">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="5ff79-695">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="5ff79-695">1OFMTH</span></span>
- <span data-ttu-id="5ff79-696">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="5ff79-696">LASTOFMTH</span></span>
- <span data-ttu-id="5ff79-697">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="5ff79-697">2OFMTH</span></span>
- <span data-ttu-id="5ff79-698">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="5ff79-698">3OFMTH</span></span>
- <span data-ttu-id="5ff79-699">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="5ff79-699">4OFMTH</span></span>
- <span data-ttu-id="5ff79-700">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="5ff79-700">5OFMTH</span></span>
- <span data-ttu-id="5ff79-701">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="5ff79-701">1N2OFMTH</span></span>
- <span data-ttu-id="5ff79-702">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="5ff79-702">3N4OFMTH</span></span>
- <span data-ttu-id="5ff79-703">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="5ff79-703">1N3OFMTH</span></span>
- <span data-ttu-id="5ff79-704">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="5ff79-704">1N4OFMTH</span></span>
- <span data-ttu-id="5ff79-705">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="5ff79-705">2N3OFMTH</span></span>
- <span data-ttu-id="5ff79-706">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="5ff79-706">2N4OFMTH</span></span>
- <span data-ttu-id="5ff79-707">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="5ff79-707">1N2N3OFMTH</span></span>
- <span data-ttu-id="5ff79-708">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="5ff79-708">1N2N4OFMTH</span></span>
- <span data-ttu-id="5ff79-709">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="5ff79-709">1N3N4OFMTH</span></span>
- <span data-ttu-id="5ff79-710">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="5ff79-710">2N3N4OFMTH</span></span>
- <span data-ttu-id="5ff79-711">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="5ff79-711">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="5ff79-712">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="5ff79-712">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="5ff79-713">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="5ff79-713">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="5ff79-714">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="5ff79-714">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="5ff79-715">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="5ff79-715">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="5ff79-716">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="5ff79-716">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="5ff79-717">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="5ff79-717">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="5ff79-718">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="5ff79-718">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="5ff79-719">Endereços</span><span class="sxs-lookup"><span data-stu-id="5ff79-719">Addresses</span></span>

<span data-ttu-id="5ff79-720">A identificação de códigos específicos de país ou região, estado e município (municipalidade) exige formatos específicos que o Dayforce e os provedores no país/na região possam reconhecer.</span><span class="sxs-lookup"><span data-stu-id="5ff79-720">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="5ff79-721">Embora o formato das cidades seja flexível, todas as cidades devem estar associadas a um estado.</span><span class="sxs-lookup"><span data-stu-id="5ff79-721">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="5ff79-722">Recursos Humanos</span><span class="sxs-lookup"><span data-stu-id="5ff79-722">Human Resources</span></span>              | <span data-ttu-id="5ff79-723">Dayforce</span><span class="sxs-lookup"><span data-stu-id="5ff79-723">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="5ff79-724">País/Região</span><span class="sxs-lookup"><span data-stu-id="5ff79-724">Country/Region</span></span>      | <span data-ttu-id="5ff79-725">Código do País</span><span class="sxs-lookup"><span data-stu-id="5ff79-725">Country Code</span></span>          |
| <span data-ttu-id="5ff79-726">CEP</span><span class="sxs-lookup"><span data-stu-id="5ff79-726">Zip/Postal Code</span></span>     | <span data-ttu-id="5ff79-727">CEP</span><span class="sxs-lookup"><span data-stu-id="5ff79-727">Postal Code</span></span>           |
| <span data-ttu-id="5ff79-728">Estadual</span><span class="sxs-lookup"><span data-stu-id="5ff79-728">State</span></span>               | <span data-ttu-id="5ff79-729">Código de estado</span><span class="sxs-lookup"><span data-stu-id="5ff79-729">State Code</span></span>            |
| <span data-ttu-id="5ff79-730">Cidade</span><span class="sxs-lookup"><span data-stu-id="5ff79-730">City</span></span>                | <span data-ttu-id="5ff79-731">Cidade</span><span class="sxs-lookup"><span data-stu-id="5ff79-731">City</span></span>                  |
| <span data-ttu-id="5ff79-732">Região</span><span class="sxs-lookup"><span data-stu-id="5ff79-732">County</span></span>              | <span data-ttu-id="5ff79-733">Município (municipalidade)</span><span class="sxs-lookup"><span data-stu-id="5ff79-733">County (Municipality)</span></span> |
| <span data-ttu-id="5ff79-734">Rua</span><span class="sxs-lookup"><span data-stu-id="5ff79-734">Street</span></span>              | <span data-ttu-id="5ff79-735">Linha de endereço 1</span><span class="sxs-lookup"><span data-stu-id="5ff79-735">Address Line 1</span></span>        |
| <span data-ttu-id="5ff79-736">Número</span><span class="sxs-lookup"><span data-stu-id="5ff79-736">Street Number</span></span>       | <span data-ttu-id="5ff79-737">Linha de endereço 2</span><span class="sxs-lookup"><span data-stu-id="5ff79-737">Address Line 2</span></span>        |
| <span data-ttu-id="5ff79-738">Complemento do edifício</span><span class="sxs-lookup"><span data-stu-id="5ff79-738">Building Complement</span></span> | <span data-ttu-id="5ff79-739">Linha de endereço 5</span><span class="sxs-lookup"><span data-stu-id="5ff79-739">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="5ff79-740">Número do passaporte</span><span class="sxs-lookup"><span data-stu-id="5ff79-740">Passport number</span></span>

<span data-ttu-id="5ff79-741">Os funcionários podem declarar as informações do passaporte.</span><span class="sxs-lookup"><span data-stu-id="5ff79-741">Employees can declare passport information.</span></span> <span data-ttu-id="5ff79-742">Essas informações são do tipo de identificação **Passaporte** e estão integradas ao Dayforce como parte das informações específicas do México de um funcionário.</span><span class="sxs-lookup"><span data-stu-id="5ff79-742">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="5ff79-743">Tipo de identificação = "Passaporte"</span><span class="sxs-lookup"><span data-stu-id="5ff79-743">Identification Type = "Passport"</span></span>
- <span data-ttu-id="5ff79-744">Data da emissão</span><span class="sxs-lookup"><span data-stu-id="5ff79-744">Issued Date</span></span>
- <span data-ttu-id="5ff79-745">Data de Vencimento</span><span class="sxs-lookup"><span data-stu-id="5ff79-745">Expiration Date</span></span>

<span data-ttu-id="5ff79-746">Os funcionários podem declarar vários números de identificação do tipo de identificação **Passaporte**.</span><span class="sxs-lookup"><span data-stu-id="5ff79-746">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="5ff79-747">No entanto, apenas a entrada atual do passaporte ativo é integrada ao Dayforce.</span><span class="sxs-lookup"><span data-stu-id="5ff79-747">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="5ff79-748">Se todas as entradas do passaporte expirarem, o passaporte emitido mais recentemente será integrado ao Dayforce.</span><span class="sxs-lookup"><span data-stu-id="5ff79-748">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]