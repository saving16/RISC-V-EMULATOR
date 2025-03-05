# RISC-V-EMULATOR
// crates/executor/src/registers.rs
#[derive(Default)]
pub struct Registers {
    x: [u64; 32],
}

impl Registers {
    #[inline(always)]
    pub fn read(&self, index: u8) -> u64 {
        if index == 0 { 0 } else { self.x[index as usize] }
    }

    #[inline(always)]
    pub fn write(&mut self, index: u8, value: u64) {
        if index != 0 {
            self.x[index as usize] = value;
        }
    }
}
