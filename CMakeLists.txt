add_library(crypto++ STATIC
        # These three must be at the top of the list
        crypto++/cryptlib.cpp
        crypto++/cpu.cpp
        crypto++/integer.cpp

        crypto++/3way.cpp
        crypto++/adler32.cpp
        crypto++/algebra.cpp
        crypto++/algparam.cpp
        crypto++/arc4.cpp
        crypto++/aria.cpp
        crypto++/aria_simd.cpp
        crypto++/ariatab.cpp
        crypto++/asn.cpp
        crypto++/authenc.cpp
        crypto++/base32.cpp
        crypto++/base64.cpp
        crypto++/basecode.cpp
        crypto++/bench1.cpp
        crypto++/bench2.cpp
        crypto++/bench3.cpp
        crypto++/bfinit.cpp
        crypto++/blake2b_simd.cpp
        crypto++/blake2.cpp
        crypto++/blake2s_simd.cpp
        crypto++/blowfish.cpp
        crypto++/blumshub.cpp
        crypto++/camellia.cpp
        crypto++/cast.cpp
        crypto++/casts.cpp
        crypto++/cbcmac.cpp
        crypto++/ccm.cpp
#         crypto++/chacha_avx.cpp
        crypto++/chacha.cpp
        crypto++/chachapoly.cpp
        crypto++/chacha_simd.cpp
        crypto++/cham.cpp
        crypto++/cham_simd.cpp
        crypto++/channels.cpp
        crypto++/cmac.cpp
        crypto++/crc.cpp
        crypto++/crc_simd.cpp
        crypto++/darn.cpp
        crypto++/datatest.cpp
        crypto++/default.cpp
        crypto++/des.cpp
        crypto++/dessp.cpp
        crypto++/dh2.cpp
        crypto++/dh.cpp
        crypto++/dll.cpp
        crypto++/dlltest.cpp
        crypto++/donna_32.cpp
        crypto++/donna_64.cpp
        crypto++/donna_sse.cpp
        crypto++/dsa.cpp
        crypto++/eax.cpp
        crypto++/ec2n.cpp
        crypto++/eccrypto.cpp
        crypto++/ecp.cpp
        crypto++/elgamal.cpp
        crypto++/emsa2.cpp
        crypto++/eprecomp.cpp
        crypto++/esign.cpp
        crypto++/files.cpp
        crypto++/filters.cpp
        crypto++/fips140.cpp
        crypto++/fipsalgt.cpp
        crypto++/fipstest.cpp
        crypto++/gcm.cpp
        crypto++/gcm_simd.cpp
        crypto++/gf2_32.cpp
        crypto++/gf256.cpp
        crypto++/gf2n.cpp
        crypto++/gf2n_simd.cpp
        crypto++/gfpcrypt.cpp
        crypto++/gost.cpp
        crypto++/gzip.cpp
        crypto++/hc128.cpp
        crypto++/hc256.cpp
        crypto++/hex.cpp
        crypto++/hight.cpp
        crypto++/hmac.cpp
        crypto++/hrtimer.cpp
        crypto++/ida.cpp
        crypto++/idea.cpp
        crypto++/iterhash.cpp
        crypto++/kalyna.cpp
        crypto++/kalynatab.cpp
        crypto++/keccak_core.cpp
        crypto++/keccak.cpp
        crypto++/keccak_simd.cpp
        crypto++/lea.cpp
        crypto++/lea_simd.cpp
        crypto++/luc.cpp
        crypto++/mars.cpp
        crypto++/marss.cpp
        crypto++/md2.cpp
        crypto++/md4.cpp
        crypto++/md5.cpp
        crypto++/misc.cpp
        crypto++/modes.cpp
        crypto++/mqueue.cpp
        crypto++/mqv.cpp
        crypto++/nbtheory.cpp
        crypto++/neon_simd.cpp
        crypto++/oaep.cpp
        crypto++/osrng.cpp
        crypto++/padlkrng.cpp
        crypto++/panama.cpp
        crypto++/pch.cpp
        crypto++/pkcspad.cpp
        crypto++/poly1305.cpp
        crypto++/polynomi.cpp
        crypto++/ppc_power7.cpp
        crypto++/ppc_power8.cpp
        crypto++/ppc_power9.cpp
        crypto++/ppc_simd.cpp
        crypto++/pssr.cpp
        crypto++/pubkey.cpp
        crypto++/queue.cpp
        crypto++/rabbit.cpp
        crypto++/rabin.cpp
        crypto++/randpool.cpp
        crypto++/rc2.cpp
        crypto++/rc5.cpp
        crypto++/rc6.cpp
        crypto++/rdrand.cpp
        crypto++/rdtables.cpp
        crypto++/regtest1.cpp
        crypto++/regtest2.cpp
        crypto++/regtest3.cpp
        crypto++/regtest4.cpp
        crypto++/rijndael.cpp
        crypto++/rijndael_simd.cpp
        crypto++/ripemd.cpp
        crypto++/rng.cpp
        crypto++/rsa.cpp
        crypto++/rw.cpp
        crypto++/safer.cpp
        crypto++/salsa.cpp
        crypto++/scrypt.cpp
        crypto++/seal.cpp
        crypto++/seed.cpp
        crypto++/serpent.cpp
        crypto++/sha3.cpp
        crypto++/shacal2.cpp
        crypto++/shacal2_simd.cpp
        crypto++/sha.cpp
        crypto++/shake.cpp
        crypto++/sharkbox.cpp
        crypto++/shark.cpp
        crypto++/sha_simd.cpp
        crypto++/simeck.cpp
        crypto++/simeck_simd.cpp
        crypto++/simon128_simd.cpp
        crypto++/simon64_simd.cpp
        crypto++/simon.cpp
        crypto++/simple.cpp
        crypto++/skipjack.cpp
        crypto++/sm3.cpp
        crypto++/sm4.cpp
        crypto++/sm4_simd.cpp
        crypto++/sosemanuk.cpp
        crypto++/speck128_simd.cpp
        crypto++/speck64_simd.cpp
        crypto++/speck.cpp
        crypto++/square.cpp
        crypto++/squaretb.cpp
        crypto++/sse_simd.cpp
        crypto++/strciphr.cpp
        crypto++/tea.cpp
        crypto++/test.cpp
        crypto++/tftables.cpp
        crypto++/threefish.cpp
        crypto++/tiger.cpp
        crypto++/tigertab.cpp
        crypto++/ttmac.cpp
        crypto++/tweetnacl.cpp
        crypto++/twofish.cpp
        crypto++/validat0.cpp
        crypto++/validat10.cpp
        crypto++/validat1.cpp
        crypto++/validat2.cpp
        crypto++/validat3.cpp
        crypto++/validat4.cpp
        crypto++/validat5.cpp
        crypto++/validat6.cpp
        crypto++/validat7.cpp
        crypto++/validat8.cpp
        crypto++/validat9.cpp
        crypto++/vmac.cpp
        crypto++/wake.cpp
        crypto++/whrlpool.cpp
        crypto++/xed25519.cpp
        crypto++/xtr.cpp
        crypto++/xtrcrypt.cpp
        crypto++/zdeflate.cpp
        crypto++/zinflate.cpp
        crypto++/zlib.cpp
    )

target_include_directories(crypto++ PUBLIC .)
target_compile_options(crypto++ PRIVATE -fPIC)
target_compile_features(crypto++ PUBLIC cxx_std_17)

if(${CMAKE_CXX_COMPILER_ID} STREQUAL "GNU")
    target_compile_definitions(crypto++ PUBLIC CRYPTOPP_DISABLE_AVX)
    target_compile_options(crypto++ PRIVATE
            -Wno-class-memaccess
            -Wno-unknown-pragmas
        )
elseif(${CMAKE_CXX_COMPILER_ID} STREQUAL "Clang")
    ## We need `CRYPTOPP_DISABLE_MIXED_ASM` because of a clang bug
    ## mentioned in the crypto++ GNUmakefile
    ## <https://bugs.llvm.org/show_bug.cgi?id=39895>
    target_compile_definitions(crypto++ PRIVATE CRYPTOPP_DISABLE_MIXED_ASM)
    target_compile_options(crypto++ PRIVATE
            -Wno-keyword-macro
            -Wno-unused-const-variable
            -Wno-unused-private-field
        )
endif()

if("${ANDROID_ABI}" STREQUAL "")
    # This assumes that we're going with x86 like systems if we're not building Android
    target_compile_options(crypto++
        PUBLIC -maes -mpclmul -msha -msse4.1 -msse4.2 -mssse3)
    install(TARGETS crypto++ LIBRARY DESTINATION lib ARCHIVE DESTINATION lib)
else()
    include(AndroidNdkModules)
    android_ndk_import_module_cpufeatures()
    target_link_libraries(crypto++ cpufeatures)
    if(${ANDROID_ABI} MATCHES "^x86")
        target_compile_options(crypto++ PUBLIC
            -maes -mpclmul -msha -msse4.1 -msse4.2 -mssse3)
    elseif(${ANDROID_ABI} STREQUAL "armeabi-v7a")
        # Setting NEON only really makes sense for this ABI
        target_compile_options(crypto++ PUBLIC -mfpu=neon)
    elseif(${ANDROID_ABI} STREQUAL "arm64-v8a")
        # There isn't anything that we need to do for this architecture
    else()
        message(FATAL_ERROR "Can't determine android architecture " ${ANDROID_ABI})
    endif()
endif()

