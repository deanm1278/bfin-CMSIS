# bfin-CMSIS
CMSIS style header files for blackfin plus DSP

These are CMSIS-style header files for the bf706 DSP processor
I built them this way because it is my preferred style. This does not mean that they are actually compliant with ARM CMSIS standard.

Registers are defined in the style:
```
#if !(defined(__ASSEMBLY__))
/* ----- TWI0_RXDATA16 : (32) TWI0 Rx Data Double-Byte Register ----- */
typedef union {
	struct {
		uint32_t VALUE:16;			/*!< bit	0..15	Rx Data 16-Bit Value	*/
		uint32_t :16;			/*!< bit	16..31	Reserved	*/
	} bit;		/*!< Structure	used for bit access		*/
	uint32_t reg;		/*!< Type	used for bit access		*/
} TWI0_RXDATA16_Type;
#define REG_TWI0_RXDATA16		(*(RwReg *)0x2004A08CUL)

#else
#define REG_TWI0_RXDATA16		(0x2004A08C) /**< \brief (TWI0) TWI0 Rx Data Double-Byte Register */
#endif
```
And groups as:
```
#if !(defined(__ASSEMBLY__))
typedef struct {
	__IO TWI0_CLKDIV_Type		CLKDIV;		/**< \brief TWI0 SCL Clock Divider Register */
	__IO TWI0_CTL_Type		CTL;		/**< \brief TWI0 Control Register */
	__IO TWI0_SLVCTL_Type		SLVCTL;		/**< \brief TWI0 Slave Mode Control Register */
	__IO TWI0_SLVSTAT_Type		SLVSTAT;		/**< \brief TWI0 Slave Mode Status Register */
	__IO TWI0_SLVADDR_Type		SLVADDR;		/**< \brief TWI0 Slave Mode Address Register */
	__IO TWI0_MSTRCTL_Type		MSTRCTL;		/**< \brief TWI0 Master Mode Control Registers */
	__IO TWI0_MSTRSTAT_Type		MSTRSTAT;		/**< \brief TWI0 Master Mode Status Register */
	__IO TWI0_MSTRADDR_Type		MSTRADDR;		/**< \brief TWI0 Master Mode Address Register */
	__IO TWI0_ISTAT_Type		ISTAT;		/**< \brief TWI0 Interrupt Status Register */
	__IO TWI0_IMSK_Type		IMSK;		/**< \brief TWI0 Interrupt Mask Register */
	__IO TWI0_FIFOCTL_Type		FIFOCTL;		/**< \brief TWI0 FIFO Control Register */
	__IO TWI0_FIFOSTAT_Type		FIFOSTAT;		/**< \brief TWI0 FIFO Status Register */
		 RoReg8		Reserved1[0x50];		
	__IO TWI0_TXDATA8_Type		TXDATA8;		/**< \brief TWI0 Tx Data Single-Byte Register */
	__IO TWI0_TXDATA16_Type		TXDATA16;		/**< \brief TWI0 Tx Data Double-Byte Register */
	__IO TWI0_RXDATA8_Type		RXDATA8;		/**< \brief TWI0 Rx Data Single-Byte Register */
	__IO TWI0_RXDATA16_Type		RXDATA16;		/**< \brief TWI0 Rx Data Double-Byte Register */
} Twi0;
#endif
```
