# Symfony ORM

#### `CustomerForTest`

```php
<?php

namespace Core\CustomerBundle\Entity;

use Core\AbstractBundle\Entity\Interfaces\EntityInterface;
use Doctrine\ORM\Mapping as ORM;
use AppBundle\Entity\Customers;

/**
 * TourCustomersForTest
 *
 * @ORM\Table(name="tour_customers_for_test", indexes={@ORM\Index(name="site_id", columns={"site_id"})})
 * @ORM\Entity
 */
class CustomersForTest implements EntityInterface
{
    /**
     * @var integer
     *
     * @ORM\Id
     * @ORM\Column(name="customer_id", type="integer", nullable=false)
     */
    private $customerId;

    /**
     * @var integer
     *
     * @ORM\Column(name="site_id", type="integer", nullable=false)
     */
    private $siteId;

    /**
     * @var integer
     *
     * @ORM\Column(name="user_id", type="integer", nullable=false)
     */
    private $userId;

    /**
     * @var Customers
     * @ORM\OneToOne(targetEntity="AppBundle\Entity\Customers", fetch="EAGER", inversedBy="id")
     * @ORM\JoinColumn(name="customer_id", referencedColumnName="id")
     */
    private $customers;

    /**
     * @param Customers $customers
     */
    public function setCustomers(Customers $customers)
    {
        $this->customers = $customers;
    }

    /**
     * @return Customers
     */
    public function getCustomers()
    {
        return $this->customers;
    }

    /**
     * Get customerId
     *
     * @return integer
     */
    public function getCustomerId()
    {
        return $this->customerId;
    }

    /**
     * Set siteId
     *
     * @param integer $siteId
     *
     * @return CustomersForTest
     */
    public function setSiteId($siteId)
    {
        $this->siteId = $siteId;

        return $this;
    }

    /**
     * Get siteId
     *
     * @return integer
     */
    public function getSiteId()
    {
        return $this->siteId;
    }

    /**
     * Set userId
     *
     * @param integer $userId
     *
     * @return CustomersForTest
     */
    public function setUserId($userId)
    {
        $this->userId = $userId;

        return $this;
    }

    /**
     * Get userId
     *
     * @return integer
     */
    public function getUserId()
    {
        return $this->userId;
    }

    /**
     * Get id
     *
     * @return int
     */
    public function getId()
    {
        return $this->getCustomerId();
    }

    /**
     * @param int $customerId
     */
    public function setCustomerId($customerId)
    {
        $this->customerId = $customerId;
    }
}

```

#### `CustomerForTestManager`

```php
//...
/**
     * @param int $customerId
     * @param int $siteId
     * @param int $adminId
     * @return bool
     */
    public function setTest($customerId, $siteId, $adminId)
    {
        $customer = $this->getObjectManager()
            ->getRepository(Customers::class)
            ->find($customerId);

        if (is_null($customer)) {
            return false;
        }

        $customerForTest = new CustomersForTest();
        $customerForTest->setSiteId($siteId);
        $customerForTest->setUserId($adminId);
        $customerForTest->setCustomers($customer);
        $customerForTest->setCustomerId($customerId);

        $this->getObjectManager()->persist($customerForTest);
        $this->getObjectManager()->flush();
        return true;
    }
//...
```
