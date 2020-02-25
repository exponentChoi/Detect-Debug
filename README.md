# Detect-Debug

+ (BOOL) tests : (NSString *) identifier
{
    #ifdef __arm64__
    asm volatile (
                  "mov x0, #26\n"
                  "mov x1, #31\n"
                  "mov x2, #0\n"
                  "mov x3, #0\n"
                  "mov x16, #0\n"
                  "svc #128\n"
                  );
    NSLog(@"Bypassed syscall() ASM64");
    #endif
    return true;

}
