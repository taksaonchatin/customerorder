# customerorder
use for learning strategy team <br>
#Create store proceduce SP_Get_Cust_Order

<a href="https://github.com/taksaonchatin/customerorder/wiki/1)-Create-SP_Get_Cust_Order" target="_blank" >Create store process : SP_Get_Cust_Order</a>



CREATE PROCEDURE [dbo].[SP_Get_Cust_Order]
	-- Add the parameters for the stored procedure here
	 
AS
BEGIN
	-- SET NOCOUNT ON added to prevent extra result sets from
	-- interfering with SELECT statements.
	SET NOCOUNT ON;

    -- Insert statements for procedure here
select cust.CustomerID 
, cust.CustomerName  , 
ord.OrderID , ord.OrderDate   
, cat.CategoryName  
, ord.ProductID 
, prod.ProductName 
from [dbo].[Orders] ord inner join 
[dbo].[Products] prod on ord.ProductID = prod.ProductID  inner join 
[dbo].[Customers] cust on cust.CustomerID = ord.CustomerID  inner join 
[dbo].[Categories]  cat on   cat.CategoryID = prod.CategoryID


END
GO
