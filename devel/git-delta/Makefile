PORTNAME=	delta
DISTVERSION=	0.9.2
PORTREVISION=	7
CATEGORIES=	devel
PKGNAMEPREFIX=	git-

MAINTAINER=	greg@unrelenting.technology
COMMENT=	Syntax-highlighting pager for git/diff

LICENSE=	MIT
LICENSE_FILE=	${WRKSRC}/LICENSE

LIB_DEPENDS+=	libgit2.so:devel/libgit2 \
		libonig.so:devel/oniguruma

USES=		cargo cpe
CPE_VENDOR=	${PORTNAME}_project
USE_GITHUB=	yes
GH_ACCOUNT=	dandavison

CARGO_CRATES=	adler-0.2.3 \
		aho-corasick-0.7.15 \
		ansi_colours-1.0.4 \
		ansi_term-0.11.0 \
		ansi_term-0.12.1 \
		arrayvec-0.5.2 \
		atty-0.2.14 \
		autocfg-1.0.1 \
		base64-0.13.0 \
		bincode-1.3.1 \
		bitflags-1.3.2 \
		box_drawing-0.1.2 \
		bstr-0.2.15 \
		bytelines-2.2.2 \
		byteorder-1.3.4 \
		cc-1.0.66 \
		cfg-if-0.1.10 \
		cfg-if-1.0.0 \
		chrono-0.4.19 \
		clap-2.33.3 \
		console-0.15.0 \
		crc32fast-1.2.1 \
		ctrlc-3.2.1 \
		dirs-3.0.2 \
		dirs-next-2.0.0 \
		dirs-sys-0.3.6 \
		dirs-sys-next-0.1.1 \
		either-1.6.1 \
		encode_unicode-0.3.6 \
		error-chain-0.12.4 \
		flate2-1.0.19 \
		fnv-1.0.7 \
		form_urlencoded-1.0.0 \
		getrandom-0.1.16 \
		getrandom-0.2.3 \
		git2-0.13.23 \
		globset-0.4.8 \
		grep-cli-0.1.6 \
		hashbrown-0.8.2 \
		heck-0.3.2 \
		hermit-abi-0.1.17 \
		idna-0.2.0 \
		indexmap-1.5.2 \
		itertools-0.10.1 \
		itoa-0.4.7 \
		jobserver-0.1.21 \
		lazy_static-1.4.0 \
		lazycell-1.3.0 \
		libc-0.2.103 \
		libgit2-sys-0.12.24+1.3.0 \
		libz-sys-1.1.2 \
		line-wrap-0.1.1 \
		linked-hash-map-0.5.3 \
		log-0.4.11 \
		matches-0.1.8 \
		memchr-2.3.4 \
		memoffset-0.6.4 \
		miniz_oxide-0.4.3 \
		nix-0.23.0 \
		num-integer-0.1.44 \
		num-traits-0.2.14 \
		once_cell-1.8.0 \
		onig-6.1.1 \
		onig_sys-69.6.0 \
		pathdiff-0.2.1 \
		percent-encoding-2.1.0 \
		pkg-config-0.3.19 \
		plist-1.0.1 \
		proc-macro-error-1.0.4 \
		proc-macro-error-attr-1.0.4 \
		proc-macro2-1.0.24 \
		quote-1.0.8 \
		redox_syscall-0.1.57 \
		redox_syscall-0.2.10 \
		redox_users-0.3.5 \
		redox_users-0.4.0 \
		regex-1.4.6 \
		regex-automata-0.1.10 \
		regex-syntax-0.6.22 \
		ryu-1.0.5 \
		safemem-0.3.3 \
		same-file-1.0.6 \
		serde-1.0.118 \
		serde_derive-1.0.118 \
		serde_json-1.0.61 \
		shell-words-1.0.0 \
		smol_str-0.1.18 \
		strsim-0.8.0 \
		structopt-0.3.25 \
		structopt-derive-0.4.18 \
		syn-1.0.57 \
		syntect-4.6.0 \
		termcolor-1.1.2 \
		terminal_size-0.1.15 \
		textwrap-0.11.0 \
		tinyvec-1.1.0 \
		tinyvec_macros-0.1.0 \
		unicode-bidi-0.3.4 \
		unicode-normalization-0.1.16 \
		unicode-segmentation-1.8.0 \
		unicode-width-0.1.9 \
		unicode-xid-0.2.1 \
		url-2.2.0 \
		utf8parse-0.2.0 \
		vcpkg-0.2.11 \
		vec_map-0.8.2 \
		version_check-0.9.2 \
		vte-0.10.1 \
		vte_generate_state_changes-0.1.1 \
		walkdir-2.3.1 \
		wasi-0.9.0+wasi-snapshot-preview1 \
		wasi-0.10.0+wasi-snapshot-preview1 \
		winapi-0.3.9 \
		winapi-i686-pc-windows-gnu-0.4.0 \
		winapi-util-0.1.5 \
		winapi-x86_64-pc-windows-gnu-0.4.0 \
		xdg-2.4.0 \
		xml-rs-0.8.3 \
		yaml-rust-0.4.5

CONFLICTS_INSTALL=	delta
PLIST_FILES=		bin/delta

OPTIONS_DEFINE=		BASH
OPTIONS_DEFAULT=	BASH
BASH_PLIST_FILES=	etc/bash_completion.d/_delta.bash

do-install-BASH-on:
	${MKDIR} ${STAGEDIR}${LOCALBASE}/etc/bash_completion.d
	${INSTALL_DATA} ${WRKSRC}/etc/completion/completion.bash \
			${STAGEDIR}${LOCALBASE}/etc/bash_completion.d/_delta.bash
post-install:
	${STRIP_CMD} ${STAGEDIR}${PREFIX}/bin/delta

.include <bsd.port.mk>
