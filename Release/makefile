################################################################################
# Automatically-generated file. Do not edit!
################################################################################

-include ../makefile.init

RM := rm -rf

# All of the sources participating in the build are defined here
-include sources.mk
-include subdir.mk
-include objects.mk

ifneq ($(MAKECMDGOALS),clean)
ifneq ($(strip $(C_DEPS)),)
-include $(C_DEPS)
endif
ifneq ($(strip $(ASM_DEPS)),)
-include $(ASM_DEPS)
endif
ifneq ($(strip $(S_DEPS)),)
-include $(S_DEPS)
endif
ifneq ($(strip $(S_UPPER_DEPS)),)
-include $(S_UPPER_DEPS)
endif
endif

-include ../makefile.defs

# Add inputs and outputs from these tool invocations to the build variables 
LSS += \
attiny13_bell_imperial.lss \

FLASH_IMAGE += \
attiny13_bell_imperial.hex \

EEPROM_IMAGE += \
attiny13_bell_imperial.eep \

SIZEDUMMY += \
sizedummy \


# All Target
all: attiny13_bell_imperial.elf secondary-outputs

# Tool invocations
attiny13_bell_imperial.elf: $(OBJS) $(USER_OBJS)
	@echo 'Building target: $@'
	@echo 'Invoking: AVR C Linker'
	avr-gcc -Wl,-Map,attiny13_bell_imperial.map -mmcu=attiny13 -o "attiny13_bell_imperial.elf" $(OBJS) $(USER_OBJS) $(LIBS)
	@echo 'Finished building target: $@'
	@echo ' '

attiny13_bell_imperial.lss: attiny13_bell_imperial.elf
	@echo 'Invoking: AVR Create Extended Listing'
	-avr-objdump -h -S attiny13_bell_imperial.elf  >"attiny13_bell_imperial.lss"
	@echo 'Finished building: $@'
	@echo ' '

attiny13_bell_imperial.hex: attiny13_bell_imperial.elf
	@echo 'Create Flash image (ihex format)'
	-avr-objcopy -R .eeprom -R .fuse -R .lock -R .signature -O ihex attiny13_bell_imperial.elf  "attiny13_bell_imperial.hex"
	@echo 'Finished building: $@'
	@echo ' '

attiny13_bell_imperial.eep: attiny13_bell_imperial.elf
	@echo 'Create eeprom image (ihex format)'
	-avr-objcopy -j .eeprom --no-change-warnings --change-section-lma .eeprom=0 -O ihex attiny13_bell_imperial.elf  "attiny13_bell_imperial.eep"
	@echo 'Finished building: $@'
	@echo ' '

sizedummy: attiny13_bell_imperial.elf
	@echo 'Invoking: Print Size'
	-avr-size --format=avr --mcu=attiny13 attiny13_bell_imperial.elf
	@echo 'Finished building: $@'
	@echo ' '

# Other Targets
clean:
	-$(RM) $(OBJS)$(C_DEPS)$(ASM_DEPS)$(EEPROM_IMAGE)$(FLASH_IMAGE)$(ELFS)$(LSS)$(S_DEPS)$(SIZEDUMMY)$(S_UPPER_DEPS) attiny13_bell_imperial.elf
	-@echo ' '

secondary-outputs: $(LSS) $(FLASH_IMAGE) $(EEPROM_IMAGE) $(SIZEDUMMY)

.PHONY: all clean dependents
.SECONDARY:

-include ../makefile.targets
