# Modify an application group {#concept_ldq_chv_vdb .concept}

## Scenarios {#section_utt_fdx_wdb .section}

When your applications use more cloud products to meet the requirements of service resizing or technical architecture improvement, you need to modify the resources in your application groups.

When the O&M and development personnel of your applications are changed, you need to modify the alarm contact groups of your application groups.

**Note:** 

-   After resources are removed from an application group, the alarm rule configured for the application group is no longer applicable to the removed instances.
-   After an instance is added to a group, the instance automatically gets associated with the alarm rule configured for the application group. You do not need to create an alarm rule for the instance.

## Modify basic information {#section_nmz_jdx_wdb .section}

To modify the application group name or the contact group, go to the details page of the target application group. In the **Basic Information** area, click the pencil icon next to the group name or contact group information. Modify the name or the contact group and click **OK**.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6147/15536511266598_en-US.png)

## Add or remove an instance {#section_g15_x41_h2b .section}

1.  To delete an instance, click the tab of the target product, find the target instance, and click **Delete** in the **Actions** column.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6147/15536511266599_en-US.png)
2.  To add an instance, click the tab of the target product and in the upper-right corner of the tab page, click **Add Instance**. On the displayed **AddResource** page, select the target instance and click **Confirm**.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6147/15536511266600_en-US.png)![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6147/15536511266601_en-US.png)

## Add a new product {#section_zwk_cq1_h2b .section}

Go to the details page of the target application group. Click **Add Product**. On the displayed AddResource page, select the target product and instance, and click **Confirm**.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6147/15536511266603_en-US.png)![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6147/15536511266604_en-US.png)

