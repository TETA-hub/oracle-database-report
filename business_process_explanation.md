Business Process Modeling - Customer Loyalty Reward System
Student: Teta Huguette | 
ID: 28982

1. BUSINESS PROCESS SCOPE
This model represents the Customer Loyalty Reward Management Process, a core MIS function for retail and service businesses. The system automates point calculation, redemption, and customer analytics to support customer relationship management (CRM) and business intelligence objectives.
Process Boundaries: From customer purchase initiation through point earning, redemption, and administrative analytics generation.

2. KEY ENTITIES AND RESPONSIBILITIES
Customer (Swimlane 1)

Initiates purchase transactions
Requests point redemption for discounts
Receives transaction receipts with updated point balance

Cashier/Sales Staff (Swimlane 2)

Records purchase details into the system
Processes redemption requests
Generates customer receipts
Communicates point balances to customers

Database System (Swimlane 3)

Automated processes triggered by transactions
Calculates loyalty points based on purchase amount and conversion rules
Updates customer point balances in real-time
Validates point availability for redemptions
Logs all transactions to audit trail for compliance
Generates business intelligence reports

Business Manager (Swimlane 4)

Reviews customer behavior analytics
Makes strategic decisions based on loyalty trends
Monitors program effectiveness

System Administrator (Swimlane 5)

Updates point conversion rules (e.g., 1 point per 100 RWF)
Maintains system configuration
Ensures data integrity


3. PROCESS FLOWS
Process 1: Purchase Transaction & Point Earning
Trigger: Customer makes a purchase

Customer presents items for purchase
Cashier records transaction details (customer ID, purchase amount, date)
Database trigger automatically:

Calculates points earned (amount ÷ conversion rate)
Updates REWARDS table with points_earned
Logs transaction to TRANSACTIONS_LOG


Cashier generates receipt showing new point balance
Customer receives confirmation

MIS Function: Automated data capture and real-time customer account management
Process 2: Point Redemption
Trigger: Customer requests to use loyalty points

Customer requests discount using accumulated points
Cashier enters redemption request
System checks: Does customer have sufficient points?

YES: Apply discount → Deduct points → Complete transaction → Generate receipt
NO: Reject request → Notify customer of insufficient points → Return to cashier


Transaction ends

MIS Function: Decision support with validation logic and transaction processing
Process 3: Administrative Management
Trigger: Periodic review or rule updates

System continuously generates BI reports from transaction data
Manager reviews customer analytics (top spenders, redemption trends, program ROI)
Admin updates point conversion rules when needed
System applies new rules to future transactions
Updated analytics reflect changes

MIS Function: Strategic decision support through data analytics and flexible configuration

4. MIS RELEVANCE
This system demonstrates Management Information System capabilities:

Transaction Processing System (TPS): Captures and processes all purchase and redemption events
Decision Support System (DSS): Provides analytics on customer loyalty behavior
Automated Business Rules: PL/SQL triggers enforce point calculations without manual intervention
Audit Compliance: Complete transaction logging for financial and regulatory requirements
Real-time Data Processing: Instant point updates enhance customer experience

Organizational Impact:

Sales Department: Identifies high-value customers for targeted marketing
Finance: Tracks liability from unredeemed points
Marketing: Measures campaign effectiveness through point redemption patterns
Executive Management: Strategic insights on customer retention ROI


5. DATA FLOWS AND HANDOFF POINTS
Critical Handoffs:

Cashier → System: Transaction data input triggers automated processing
System → Cashier: Calculated results return for customer communication
System → Manager: Automated report generation for analytics
Admin → System: Configuration changes affect future calculations

Decision Points:

Point Sufficiency Check: Binary decision determines redemption approval
Rule Application: System validates transactions against current conversion rates


6. ANALYTICS OPPORTUNITIES
The database design supports:

Customer Segmentation: Identify top 20% of customers by points earned
Redemption Rate Analysis: Calculate percentage of earned points redeemed
Purchase Pattern Recognition: Seasonal trends, average transaction value
Program ROI Measurement: Cost of rewards vs. increased customer lifetime value
Fraud Detection: Unusual redemption patterns flagged in audit logs


7. TECHNICAL IMPLEMENTATION NOTES
PL/SQL Components Mapped to Process:

Triggers: Automatic point calculation on PURCHASES table INSERT
Procedures: Manual redemption processing with validation
Functions: Point balance calculation, redemption eligibility check
Cursors: Batch processing for periodic analytics generation
Packages: Group loyalty management functions (LOYALTY_PKG)

Tables Involved:

CUSTOMERS (customer master data)
PURCHASES (transaction records)
REWARDS (point ledger)
POINT_RULES (conversion configuration)
TRANSACTIONS_LOG (audit trail)