# SPP Porting Project: High-Level Process Outline

## 1. Core Procurement & Warehouse (Desk/App Origin)
- **Purchase Order**: Synching (25spp -> spp15)
- **Purchase Receipt**: Not Synching (Requires Attention)
- **RM Quality Inspection**: To Check
- **Transfer to Chemical Bin**: Synching
- **Transfer to Packet Warehouse**: Synching
- **Batch Aggregation**: Synching

## 2. Console APP Operations (Production Phase)
- **Master Batch Mixing**: Synching
- **Compound Mixing**: Synching
- **Compound Inspection**: Synching
- **Deviation Entry**: Active (Console App)
- **Scrap Entry**: Active (Console App)

## 3. Legacy Screen Porting (Manufacturing & Finishing)
- **Sheeting Entry / Cutbit Transfer / Blanking DC**: Synching
- **Moulding Production Entry**: To Check
- **Sublot Creation**: To Check
- **Deflashing (Despatch/Receipt/Return)**: Synching
- **Bin Movement / Bulk Clip Release**: Synching
- **Line/Patrol/Lot Inspection**: To Check
- **Final Inspection Entry**: To Check
- **U1 Receipt / Despatch to U1**: To Check
- **Packing**: To Check
- **Sales Invoice**: Working (Bulk Invoice mode)

## 4. Priority Tasks
1. **Fix Purchase Receipt Sync**: Investigate why it is "Not Synching".
2. **Validate "To Check" Processes**: Prioritize Moulding and Inspection processes.
3. **Standardize Sync Architecture**: Ensure all processes use the `apply_bridge_result` method.
