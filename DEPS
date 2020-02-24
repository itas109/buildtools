use_relative_paths = True

vars = {
  'chromium_url': 'https://chromium.googlesource.com',

  #
  # TODO(crbug.com/941824): The values below need to be kept in sync
  # between //DEPS and //buildtools/DEPS, so if you're updating one,
  # update the other. There is a presubmit check that checks that
  # you've done so; if you are adding new tools to //buildtools and
  # hence new revisions to this list, make sure you update the
  # _CheckBuildtoolsRevsAreInSync in PRESUBMIT.py to include the additional
  # revisions.
  #

  # GN CIPD package version.
  'gn_version': 'git_revision:4166e9fbc1fa5ceab69b69710a0f8b430c50127b',

  # When changing these, also update the svn revisions in deps_revisions.gni
  'clang_format_revision': '96636aa0e9f047f17447f2d45a094d0b59ed7917',
  # TODO(crbug.com/1054245): Rename these vars back to their original name
  # once libassistant's copy of buildtools rolls up to the rename.
  'libcxx_revision_v2':       'd9040c75cfea5928c804ab7c235fed06a63f743a',
  'libcxxabi_revision_v2':    '196ba1aaa8ac285d94f4ea8d9836390a45360533',
  'libunwind_revision_v2':    '43bb9f872232f531bac80093ceb4de61c64b9ab7',
}

deps = {
  'clang_format/script':
    Var('chromium_url') + '/chromium/llvm-project/cfe/tools/clang-format.git@' +
    Var('clang_format_revision'),
  'linux64': {
    'packages': [
      {
        'package': 'gn/gn/linux-amd64',
        'version': Var('gn_version'),
      }
    ],
    'dep_type': 'cipd',
    'condition': 'host_os == "linux"',
  },
  'mac': {
    'packages': [
      {
        'package': 'gn/gn/mac-amd64',
        'version': Var('gn_version'),
      }
    ],
    'dep_type': 'cipd',
    'condition': 'host_os == "mac"',
  },
  'third_party/libc++/trunk':
    Var('chromium_url') +
    '/external/github.com/llvm/llvm-project/libcxx.git' + '@' +
    Var('libcxx_revision_v2'),
  'third_party/libc++abi/trunk':
    Var('chromium_url') +
    '/external/github.com/llvm/llvm-project/libcxxabi.git' + '@' +
    Var('libcxxabi_revision_v2'),
  'third_party/libunwind/trunk':
    Var('chromium_url') +
    '/external/github.com/llvm/llvm-project/libunwind.git' + '@' +
    Var('libunwind_revision_v2'),
  'win': {
    'packages': [
      {
        'package': 'gn/gn/windows-amd64',
        'version': Var('gn_version'),
      }
    ],
    'dep_type': 'cipd',
    'condition': 'host_os == "win"',
  },
}
