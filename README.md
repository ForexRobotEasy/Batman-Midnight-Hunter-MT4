# Batman Midnight Hunter MT4 - ReadMe

This ReadMe file provides an overview and explanation of the code for the Batman Midnight Hunter MT4 Expert Advisor. Please note that ForexRobotEasy is not the official developer of this product. We are only providing a sample code that can work as described in the product.

For detailed reviews and trading results of this product, please visit [this link](https://forexroboteasy.com/forex-robot-review/batman-midnight-hunter-mt4-smart-night-scalping-review/).

## Global Variables

- `stopLoss`: Fixed Stop Loss level (default: 30)
- `takeProfit`: Fixed Take Profit level (default: 50)
- `maxSpread`: Maximum allowed spread for trading (default: 2.0)
- `suffixPrefixSupported`: Flag to check if suffix or prefix is supported by the broker (default: true)
- `spreadControlEnabled`: Flag to enable spread control function (default: true)

## Expert Advisor Functions

### Initialization Function - `OnInit()`

This function is called during the initialization of the Expert Advisor. It checks if the broker supports suffix or prefix. If not supported, it prints an error message and returns `INIT_FAILED`. Otherwise, it prints the initial settings and returns `INIT_SUCCEEDED`.

### Deinitialization Function - `OnDeinit(const int reason)`

This function is called during the deinitialization of the Expert Advisor. It simply prints a success message.

### Tick Event Handler - `OnTick()`

This function is called on each tick of the market. It first checks if spread control is enabled. If enabled, it fetches the current spread and checks if it is within the acceptable range specified by `maxSpread`. If the spread is too high, it prints a message and skips the trade.

If the spread is within the acceptable range, it generates pending order prices for buying and selling. It then places the pending orders using `OrderSend()` function. The function returns the ticket numbers of the placed orders.

If the orders are executed successfully, it prints a success message and enters a while loop to monitor the pending orders. The loop waits until trading is allowed. Once trading is allowed, it closes the pending orders using `OrderClose()` function. The function returns a boolean value indicating whether the orders were closed successfully or not.

If the orders are closed successfully, it prints a success message. Otherwise, it prints a failure message.

## Product Description

The Batman Midnight Hunter MT4 Expert Advisor is a smart night scalping robot developed by the Forex Robot Easy Team. It is designed to trade during the night hours, taking advantage of potential market movements. The Expert Advisor uses fixed stop loss and take profit levels as specified in the global variables.

The key features of the Batman Midnight Hunter MT4 Expert Advisor include:
- Fixed Stop Loss and Take Profit levels for risk management
- Maximum allowed spread control to avoid trading during high spread periods
- Support for suffix or prefix by the broker to ensure compatibility
- Smart night scalping strategy for potential profit opportunities

Please note that this code is a sample and may require further customization or optimization based on individual trading preferences and market conditions. To find the official developer of this product and explore more advanced features, please refer to MQL5.
