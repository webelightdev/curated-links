# Composer Lint #
- Install composer plugin globally.

    `wget https://github.com/FriendsOfPHP/PHP-CS-Fixer/releases/download/v2.14.0/php-cs-fixer.phar -O php-cs-fixer`

    or

    `composer global require friendsofphp/php-cs-fixer`
- Run in terminal `export PATH="$PATH:$HOME/.composer/vendor/bin"`
- Restart terminal

- Then update composer.json of current project directory.
    ```
    "require-dev": {
        "friendsofphp/php-cs-fixer": "^2.14",
    }
    ```
- Run `composer update`
- Make file on root directory of project with name `.php_cs.dist`.
- put the below content in `.php_cs.dist`.

    ```
    $finder = PhpCsFixer\Finder::create()
        ->notPath('bootstrap/cache')
        ->notPath('node_modules')
        ->notPath('storage')
        ->notPath('vendor')
        ->name('*.php')
        ->notName('*.blade.php')
        ->ignoreDotFiles(true)
        ->ignoreVCS(true)
        ->in(__DIR__)
    ;

    return PhpCsFixer\Config::create()
        ->setRiskyAllowed(true)
        ->setRules([
            'align_multiline_comment' => ['comment_type' => 'phpdocs_only'],
            'array_syntax' => ['syntax' => 'short'],
            'binary_operator_spaces' => ['operators' => ['>>' => 'align', '=>' => 'align_single_space'], 'default' => 'single_space'],
            'blank_line_after_namespace' => true,
            'blank_line_after_opening_tag' => true,
            'blank_line_before_return' => true,
            'blank_line_before_statement' => ['statements' => ['break', 'continue', 'declare', 'return', 'throw', 'try']],
            'braces' => ['allow_single_line_closure' => false, 'position_after_anonymous_constructs' => 'same', 'position_after_control_structures' => 'same', 'position_after_functions_and_oop_constructs' => 'next'],
            'cast_spaces' => ['space' => 'single'],
            'class_attributes_separation' => ['elements' => ['const', 'method', 'property']],
            'class_definition' => ['multiLineExtendsEachSingleLine' => false, 'singleItemSingleLine' => false, 'singleLine' => false],
            'concat_space' => ['spacing' => 'one'],
            'declare_equal_normalize' => ['space' => 'none'],
            'elseif' => true,
            'encoding' => true,
            'full_opening_tag' => true,
            'function_declaration' => ['closure_function_spacing' => 'one'],
            'function_typehint_space' => true,
            'heredoc_to_nowdoc' => true,
            'include' => true,
            'increment_style' => ['style' => 'post'],
            'indentation_type' => true,
            'line_ending' => true,
            'linebreak_after_opening_tag' => true,
            'lowercase_cast' => true,
            'lowercase_constants' => true,
            'lowercase_keywords' => true,
            'magic_constant_casing' => true,
            'method_argument_space' => ['ensure_fully_multiline' => false, 'keep_multiple_spaces_after_comma' => false],
            'multiline_whitespace_before_semicolons' => ['strategy' => 'no_multi_line'],
            'native_function_casing' => true,
            'no_alias_functions' => true,
            'no_blank_lines_after_class_opening' => true,
            'no_blank_lines_after_phpdoc' => true,
            'no_closing_tag' => true,
            'no_empty_phpdoc' => true,
            'no_empty_statement' => true,
            'no_extra_blank_lines' => ['tokens' => ['extra']],
            'no_leading_import_slash' => true,
            'no_leading_namespace_whitespace' => true,
            'no_mixed_echo_print' => ['use' => 'echo'],
            'no_multiline_whitespace_around_double_arrow' => true,
            'no_short_bool_cast' => true,
            'no_singleline_whitespace_before_semicolons' => true,
            'no_spaces_after_function_name' => true,
            'no_spaces_around_offset' => ['positions' => ['inside']],
            'no_spaces_inside_parenthesis' => true,
            'no_trailing_comma_in_list_call' => true,
            'no_trailing_comma_in_singleline_array' => true,
            'no_trailing_whitespace' => true,
            'no_trailing_whitespace_in_comment' => true,
            'no_unneeded_control_parentheses' => ['statements' => ['break', 'clone', 'continue', 'echo_print', 'return', 'switch_case', 'yield']],
            'no_unreachable_default_argument_value' => true,
            'no_unused_imports' => true,
            'no_useless_return' => true,
            'no_whitespace_before_comma_in_array' => true,
            'no_whitespace_in_blank_line' => true,
            'normalize_index_brace' => true,
            'object_operator_without_whitespace' => true,
            'ordered_class_elements' => ['order' => ['use_trait', 'constant_public', 'constant_protected', 'constant_private', 'property_public', 'property_protected', 'property_private', 'construct', 'destruct', 'magic', 'phpunit', 'method_public', 'method_protected', 'method_private'], 'sortAlgorithm' => 'none'],
            'ordered_imports' => ['importsOrder' => null, 'sortAlgorithm' => 'length'],
            'phpdoc_add_missing_param_annotation' => true,
            'phpdoc_align' => ['tags' => ['param', 'return', 'throws', 'type', 'var']],
            'phpdoc_indent' => true,
            'phpdoc_inline_tag' => true,
            'phpdoc_no_useless_inheritdoc' => true,
            'phpdoc_order' => true,
            'phpdoc_return_self_reference' => ['replacements' => ['this' => '$this', '@this' => '$this', '$self' => 'self', '@self' => 'self', '$static' => 'static', '@static' => 'static']],
            'phpdoc_scalar' => true,
            'phpdoc_single_line_var_spacing' => true,
            'phpdoc_summary' => true,
            'phpdoc_to_comment' => true,
            'phpdoc_trim' => true,
            'phpdoc_types' => true,
            'phpdoc_var_without_name' => true,
            'psr4' => true,
            'self_accessor' => true,
            'short_scalar_cast' => true,
            'simplified_null_return' => true,
            'single_blank_line_at_eof' => true,
            'single_class_element_per_statement' => ['elements' => ['const', 'property']],
            'single_import_per_statement' => true,
            'single_line_after_imports' => true,
            'single_line_comment_style' => ['comment_types' => ['hash']],
            'single_quote' => ['strings_containing_single_quote_chars' => false],
            'space_after_semicolon' => ['remove_in_empty_for_expressions' => false],
            'standardize_not_equals' => true,
            'switch_case_semicolon_to_colon' => true,
            'switch_case_space' => true,
            'ternary_operator_spaces' => true,
            'ternary_to_null_coalescing' => true,
            'trailing_comma_in_multiline_array' => true,
            'trim_array_spaces' => true,
            'unary_operator_spaces' => true,
            'visibility_required' => ['elements' => ['property', 'method']],
            'whitespace_after_comma_in_array' => true,
        ])
        ->setFinder($finder)
    ;
    ```

- then update `composer.json` with
    
    ```
    "scripts": {
        "lint": [
            "@php vendor/bin/php-cs-fixer fix --config=.php_cs.dist --verbose --diff --using-cache=no"
        ],
    },
    ```
- Now run `composer lint`